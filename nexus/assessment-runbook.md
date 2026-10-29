# ScubaGear Assessment Runbook

Procedure for running ScubaGear in a Nexus client engagement. Always check the [upstream documentation](https://github.com/cisagov/ScubaGear) for current prerequisites, permissions, and parameters.

## 0. Before you start

- [ ] Signed SOW and written authorization naming the M365 tenant in scope
- [ ] Client IT contact available to grant and later remove access
- [ ] Evidence folder created: `<Client>/<YYYY-MM-DD>-scubagear/`
- [ ] Windows workstation with PowerShell 5.1 (per upstream requirements)

## 1. Access (read-only, least privilege)

- Request a **temporary** account or service principal with the read-only roles listed in the upstream permissions documentation (Global Reader covers most checks; some products need additional read roles).
- Never run under the client's day-to-day Global Admin account.
- Record who granted access, when, and the planned removal date.

## 2. Prepare

```powershell
Install-Module -Name ScubaGear
Initialize-SCuBA          # installs dependencies
Get-Module ScubaGear -ListAvailable   # record the version
```

## 3. Run

```powershell
# All supported M365 products
Invoke-SCuBA -ProductNames *

# Or a subset, e.g. Entra ID and Exchange Online
Invoke-SCuBA -ProductNames aad, exo
```

ScubaGear writes an HTML report plus JSON/CSV results to a dated output folder. Copy the whole folder to the client evidence folder and record SHA-256 hashes.

## 4. Triage

1. Start with failed **"shall"** requirements, then "should" requirements.
2. Confirm each failure in the admin portal; document compensating controls (for example, a third-party email gateway in place of Defender).
3. Rate on the Nexus 5×5 likelihood × impact scale.
4. Map to frameworks using [`framework-mapping.md`](framework-mapping.md).
5. Prioritize identity first (MFA, legacy auth, privileged roles), then email security, then sharing and logging.

## 5. Report and close out

- Complete [`client-report-checklist.md`](client-report-checklist.md).
- Have the client remove the temporary account / role assignments; confirm in writing.
- Schedule the re-assessment (quarterly for vCISO clients).

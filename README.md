Sign-in Frequency = 12 hoursAll cloud apps
All users (non-compliant devices)Session → Sign-in frequency → 12 hours (non-persistent)Grant access+6–8 %Prevents indefinite use of stolen refresh tokensBlock Device Code Flow & PRT from Untrusted LocationsAll usersClient apps → Device code authentication & Windows broker (PRT) → Block outside “Trusted named locations”Block access+5–7 %Stops rising device-code phishing and rogue PRT acquisitionTrusted Named Locations + Block OutsidePrivileged roles + sensitive appsLocations → Define corporate IPs as “Trusted”
New policy → Block access from non-trusted locationsBlock access+6–8 %Geo-fencing for privileged and high-value accessApp Enforced Restrictions (Exchange)All usersPowerShell: Set-OrganizationConfig -AppEnforcedRestrictionsEnabled $trueBlocks classic Outlook, IMAP, POP, etc.+8–10 %Final nail in legacy protocol coffin even if legacy auth slips throughContinuous Access Evaluation (CAE)M365 workloads (automatic)Enabled by default for Exchange, SharePoint, Teams, OneDriveReal-time token revocation on risk events+4–6 %Near-instant revocation on user risk, token theft, or policy violationToken Protection – Bound TokensAll Windows devicesIntune → Configuration profiles → Windows Hello for Business → Require token protection = EnabledBinds PRT/refresh tokens to TPM+5–7 %Renders stolen tokens useless even if attacker has passkey or password
Staged Rollout (Mandatory to avoid outages)

Create three dynamic groups: Pilot-MFA, EarlyAdopters-MFA, AllUsers-MFA
Every new policy above starts with Pilot → EarlyAdopters → AllUsers over 4–6 weeks

End of Phase 2 Deliverables (Week 12)

Legacy authentication = 0 (verified in Sign-in logs)
100 % phishing-resistant MFA enforced (reports show only FIDO2/CBA/Passkey)
Number matching enforced tenant-wide
Token protection deployed via Intune
Secure Score ≥ 97 %

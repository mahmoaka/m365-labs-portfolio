# Lab 01 - Identity & Conditional Access
**Date:** 2025-09-28

## Objective
Enable MFA and Condtional Access policies for test users in Microsoft 365.

## Prerequisities 
- Microsoft 365 Business Premium Tenant
- Global Admin Account
- Two test users: alice@greywirelab.com and bob@greywirelab.com

## Steps Performed
1. Created test users in Microsoft 365 Admin Center.
2. Assigned Business Premium Licenses. 
3. Enabled MFA for users and attempted MFA registration, but intial login failed due to incomplete setup.
4. Re-enforced MFA registration via Microsoft 365 Portal:
    - Admin → Users → Active Users → Select User → Authentication Method → Require re-registertration
5. Configured Conditional Access Policy to block sign-in from no-home IPs.

## Screenshots
- ![MFA Setup](01-identity-security/screenshots/01-mfa-setup.png)
- ![MFA Setup](01-identity-security/screenshots/02-mfa-setup.png)
- `screenshots/02-conditional-access-policy.png`

## Outcome / Lessons Learned
- MFA successfully enforced. 
- Condtional Access blocked external logins.
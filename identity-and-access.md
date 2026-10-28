# Identity and access

The scenario included direct user permissions on FILE01, an overprivileged backup account, and a former consultant who still had access.

## File permissions

I proposed using AGDLP to make access easier to manage:

`Finance user → GG_FINANCE_USERS → DL_FILE01_FINANCE_MODIFY → Finance folder`

Users join groups for their department or role. Resource groups receive permissions on the folders. This avoids assigning permissions separately to every person.

| Folder | Proposed access |
| --- | --- |
| Finance | Modify for the approved Finance group |
| HR | Modify for the approved HR group |
| Shared | Separate Read and Modify groups |
| Other department folders | Access through the relevant department groups |

Share and NTFS permissions both need to be checked, including inheritance and existing Deny entries. Tests should use ordinary accounts from both authorized and unauthorized roles.

## Account changes

- Separate daily work accounts from administrative accounts.
- Check the backup application's requirements before removing unnecessary Domain Admin privileges from its service account.
- Disable former employees' and consultants' access promptly.
- Review old group memberships when someone changes roles.

These changes are proposed; no account or permission changes are claimed as implemented.

[Back to overview](README.md)

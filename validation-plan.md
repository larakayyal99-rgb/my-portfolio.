# Test plan

These tests describe how I would check the design in an isolated lab. They have not been run.

| Test | Expected result | Status |
| --- | --- | --- |
| Obtain a USERS DHCP lease | Correct pool, /23 mask, gateway, and internal DNS | Not run |
| Resolve internal and external names from USERS | DNS returns the expected answers | Not run |
| Connect from GUEST to internal services | Access is blocked | Not run |
| Resolve an external name and browse from GUEST | Approved guest internet access works | Not run |
| Connect from USERS to WEB01 on TCP 443 | HTTPS is reachable | Not run |
| Attempt administration from an ordinary user device | Unapproved access is blocked | Not run |
| Use the approved administration path | Required administration works | Not run |
| Open Finance files with authorized and unrelated accounts | Permissions match the access design | Not run |
| Compare FILE01 before and after a backup schedule change | File access improves without compromising recovery needs | Not run |
| Restore FILE01 in isolation | Data, permissions, and service access work within approved recovery targets | Not run |

For each test, I would record the setup, procedure, actual result, and supporting output. Failed tests would be documented alongside successful ones.

[Back to overview](README.md)

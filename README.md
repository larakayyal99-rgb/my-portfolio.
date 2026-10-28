# Network Security & Infrastructure

Course project · Cyber Security Engineering · Medieinstitutet

For this assignment, I reviewed the IT environment of Northstar Engineering AB, a fictional company with around 145 users. The task was to identify weaknesses and propose a design that could support at least 250 users.

## My approach

The main problems were a flat network, guest access to internal systems, and accounts with more permissions than they needed. I focused on separating devices by purpose and making access easier to control.

- **Network design:** Proposed seven segments for users, servers, management, guests, production, IoT, and printers. Used different subnet sizes to match their needs.
- **Access control:** Proposed OPNsense traffic rules and group-based file permissions using Active Directory and AGDLP.
- **Troubleshooting:** Analyzed two supplied cases: a slow file server during backup and an unavailable HTTPS service. Used the evidence to narrow down likely causes and plan verification.
- **Recovery:** Defined a restore-test procedure for FILE01, with proposed targets of four hours for data loss and two hours for recovery.

## One example

FILE01's disk activity reached 94–100% during backup, while CPU stayed around 20–27%. That pointed me toward storage contention rather than CPU load. I proposed changing the backup schedule, then comparing storage performance and user experience before and after the change.

## Project notes

[Network design](network-design.md) · [Access control](identity-and-access.md) · [Troubleshooting](troubleshooting.md) · [Operations & recovery](operations-and-recovery.md) · [Test plan](validation-plan.md)

This was a design and analysis assignment. The observations came from the course scenario; I have not deployed or tested the proposed environment.

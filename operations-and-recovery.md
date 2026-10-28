# Operations and recovery

## Monitoring

I proposed tracking CPU, RAM, storage performance and capacity, network availability, important services, and backup results. Monitoring should be compared with a baseline and supported by system, application, security, and firewall logs.

FILE01 shows why this matters: a backup can finish successfully while still making the file server slow for users.

## Backup and restore

For FILE01, I proposed:

| Objective | Target |
| --- | --- |
| RPO: acceptable data-loss interval | 4 hours |
| RTO: time to restore the service | 2 hours |

These targets need business approval and a restore test before they can be treated as achievable.

The restore procedure would use an isolated environment, a recovery point within the RPO, and checks of files, permissions, and service access. I proposed testing quarterly and after significant backup changes. No restore results are included.

## Priorities

First, block guest access to internal resources and disable obsolete access. Next, review administrative and service accounts, file permissions, and backup health. Then introduce segmentation, monitoring, and documented recovery procedures.

Before a firewall change, save the configuration and prepare a rollback plan. Afterward, test both required access and traffic that should remain blocked.

Virtualization also needs a separate availability plan: several VMs on one host still share that host's failure risk, along with any shared storage or network dependency.

[Back to overview](README.md)

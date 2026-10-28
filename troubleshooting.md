# Troubleshooting

These cases use observations provided in the assignment.

## FILE01: slow access during backup

The backup starts at 13:00. Disk activity then rises to about 94–100%, while CPU stays around 20–27% and memory remains near its normal level.

My first hypothesis was storage contention: the backup and users may be competing for disk resources. The timing supports this, but does not prove the cause by itself.

I would compare backup timestamps with disk latency, queue depth, and user reports. Then I would move or tune the backup job and compare performance under similar conditions. The change also needs to preserve the required recovery points.

## WEB01: HTTPS unavailable

DNS resolves and ping succeeds, but the TCP 443 test fails. OPNsense shows a matching PASS entry, and the web application service is stopped.

The stopped service is the strongest lead. Ping alone does not establish that HTTPS works, and a firewall PASS does not prove an end-to-end connection.

I would check the service logs and dependencies, investigate why it stopped, and start it when appropriate. Verification would include service status, `Test-NetConnection WEB01 -Port 443`, and opening the portal from a client.

## What I took from the cases

Start with the evidence, narrow the scope, and test a hypothesis before changing settings. A fix needs verification from the user's side as well as the server's.

[Back to overview](README.md)

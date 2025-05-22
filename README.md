Oracle Integration Cloud Disaster Recovery (OIC-DR) Walkthrough
Overview
This guide explains the Disaster Recovery (DR) process for Oracle Integration Cloud (OIC), based on a walkthrough video demonstration. The procedure illustrates how users can perform a failover operation to a standby region in the event of an outage or planned maintenance.
Key Components
Primary OIC Instance: Active instance handling production traffic.


Standby OIC Instance: Configured to take over during a failover.


Disaster Recovery Console: Interface used to trigger and monitor failover and switchover actions.


DNS and Routing: Updated automatically (or manually, depending on setup) during DR operations to redirect traffic.


Steps Shown in the Walkthrough
1. Accessing the DR Dashboard
Navigate to the Oracle Cloud Console.


Go to Disaster Recovery under OIC Resources.


Confirm the Primary and Standby regions and current replication status.


2. Initiating the Switchover
Select the Switchover option from the DR console.


Confirm the action and review dependencies.


The UI displays a progress bar indicating:


Configuration validation


Resource replication


Routing updates


3. Monitoring the Failover Process
Track each step through the Execution Plan Viewer.


Status indicators:


✅ Green checkmarks: successful steps


🕒 Loading spinner: steps in progress


❌ Red icons: failed or blocked steps (if any)


4. Validating the Standby Environment
After switchover, the previous standby becomes the active instance.


Verify:


Integrations are present and enabled.


Connectivity with external systems is functioning.


Monitoring and alerting tools reflect the new primary region.


5. Post-Failover Checks
Review logs and metrics for any missed syncs.


Perform test transactions to confirm readiness.


Optionally, schedule a switchover back to the original primary once stable.


Notes
The failover process involves zero data loss if replication is current.


DR actions are role-based access controlled (RBAC).


Integrations paused during switchover may require manual restart if not auto-enabled.


Troubleshooting
Symptom
Possible Cause
Resolution
Replication status stuck
Network issues
Check connectivity between regions
Failover fails midway
Configuration drift
Validate both environments are in sync
DNS not updating
Manual DNS setup
Update DNS records or automate via OCI DNS

Resources
Oracle Documentation: OIC DR Setup


OCI CLI for DR Automation


Contact Oracle Support for any production-impacting DR failure scenarios.




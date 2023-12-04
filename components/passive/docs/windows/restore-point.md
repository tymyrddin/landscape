# Creating a Windows restore point

In case the Windows machine is compromised, going back to a previous restore point may fix the issue. If it exists:

* Type Create a restore point in the search box
* System Properties -> C drive and click the Create button
* Add a description to the system restore point and click Create
* System Restore Point Creating Process
* The system restore point process will begin (wait, wait, wait for it)
* The restore point was created successfully

#
## On windows intrusion detection systems

OSSEC only supports Windows systems as agents, but they will require an OSSEC server to function, so for home and small organisations, we best use an eventlog analyzer.


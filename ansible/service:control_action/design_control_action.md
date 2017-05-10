#  Ansible Control Actions

Pivotal Tracker Project: [Ansible - Service, Automate, Control, Alert](https://www.pivotaltracker.com/n/projects/1937537)

Based on the UI screens in the presentation for the Ansible Playbook and Control Action we were thinking of the following approach:

- When an Action is being defined we would use the same UI as when creating a Service Template, which will link the playbook, repo, dialog with default values.
- A Control Action would store a reference to the Service Template
- A Control Action would also store the inventory reference (localhost, alert target or user defined)
- When an Action is executed, we would order the Service silently with no user interaction and pass in the appropriate inventory.
- The Action would only point to a Provisioning State Machine (no Reconfigure/Retire)
- Each execution of the Action would result in a Task/Request being created which would allow us to keep an Audit trail.
- The extra vars for the Playbook can be defined in the Service Dialog, and at execution time we would pick up the default values from the ServiceDialog.

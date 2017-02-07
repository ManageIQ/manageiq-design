#  Ansible Inside Design

Pivotal Tracker Project
https://www.pivotaltracker.com/n/projects/1937407

## Appliance Install

The goal is to be able to fully install all ansible Tower binaries on the appliance at build time. This way the only thing that needs to be done (once appliance configuration is done) when the “ansible” role is enabled is start the local Ansible service. Ansible Tower will be configured to connect to the same PostgreSQL DB as the appliance and that will be done when the DB is configured in the appliance console.

Currently Ansible Tower has a single installation script that runs as a playbook. This installation installs all the binaries, configures the database, nginx (http server) and starts all necessary services. We would need to break that process up into these three phases, at a minimum.

### Build
Install Ansible Tower binaries as part of the appliance build process.

### Configuration
Configure things like http ports and DB connections. Some of this can be done during the appliance build. Other configurations will need to be done when the appliance is configured.

### Service Starting and Stopping
The Ansible Tower service should not be started until the “ansible” role is enabled by a CF admin. Therefore, we would need to control the service from CF.

## Server role
We will minimally need one new role to control making the embedded Ansible Tower available for running playbooks. Enabling the role should start ansible Tower on the appliance. Likewise, disabling the role should stop it.

### Region, Zone and Failover
We’ll start with a single Tower instance per region while investigating Ansible clustering. The new “embedded_ansible” role will be scoped at the region level. It should support failover, however, to do so, it will be necessary to have the same encryption key (the equivalent to our v2_key) on all appliances having the role enabled.
We were thinking that we may be able to leverage the existing mechanism in the appliance console to copy the Ansible key along with the v2_key. Doing this would also make it necessary for us to create the Ansible key at the same time that the v2_key is created to ensure that they are managed in lock step. This all requires additional research. Specifically, whether we can create the Ansible key outside of the ansible install.

### Multiple Ansible Tower instances in the same region

### Development Tasks
- New role named “ansible”
- One active per region (until we can support a clustered Tower installation)
- Should support failover
- When role is enabled -
  - Start ansible service on appliance
  - Create built-in ansible Inside provider (if not existing already)
- When role is disabled -
  - Stop ansible service on appliance
  - Anything else?

## Upstream/Downstream
Given that Ansible Tower is not current open source, it will not be possible to include it on an upstream appliance. Therefore, there needs to be a dynamic mechanism for hiding or disabling features built on top of Ansible Inside when Tower is not present. It needs to be dynamic because a manually installing Ansible Tower on a CF appliance also needs to be supported.

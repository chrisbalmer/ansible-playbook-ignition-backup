# Ignition Backup Playbook

This playbook will backup user data from an Inductive Automation Ignition server. From the Ignition web page:

*Backs up the user data inside this Ignition Gateway server. This includes all projects, drivers, images, and configuration, but not the modules.*

## Required Variables

**Directory to save backups to:**
```yaml
backup_directory: ~/
```
Backups will go into `{{ backup_directory }}/{{ ignition_server }}`, so each Ignition server will get its own directory within the backup directory for backups.


**Ignition Instances**
```yaml
ignition_servers:
  - ignition_server: ignition.example.com
    ignition_port: 8088
    username: admin
    password: password
```
A list of the instances to backup. This covers the hostname of the instance, the port and the login details.

*Please make sure you're not using the default password for production Ignition instances.*

## Hosts

The host you run this on is the host you wish to save the backup file to. If you want to save copies to multiple locations, specify multiple hosts with some hosts in other locations. This will give you off site backups. The provided `hosts` file shows an example of this setup.

## Testing

The provided `hosts` file is an example file with variables used in testing. The testing was performed against the [Ignition docker image](https://hub.docker.com/r/kcollins/ignition) built by [Kevin Collins](https://github.com/thirdgen88).
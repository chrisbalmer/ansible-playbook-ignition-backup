# Ignition Backup Playbook

This playbook will backup user data from an Inductive Automation Ignition server. From the Ignition web page:

*Backs up the user data inside this Ignition Gateway server. This includes all projects, drivers, images, and configuration, but not the modules.*

## Required Variables

As a trial run, this playbook doesn't support multiple Ignition instances. It will be updated shortly to handle more than one instance. In the meantime, these variables are required:


**Directory to save backups to:**
```yaml
backup_directory: ~/
```

**Ignition instance to pull backups from:**
```yaml
ignition_server: 172.21.21.194
```

**Port of the Ignition instance:**
```yaml
ignition_port: 8088
```

**Ignition instance login:**
```yaml
username: admin
password: password
```

*Please make sure you're not using the default password for production Ignition instances.*

## Hosts

The host you run this on is the host you wish to save the backup file to. If you want to save copies to multiple locations, specify multiple hosts with some hosts in other locations. This will give you off site backups.

## Testing

The provided `hosts` file is an example file with variables used in testing. The testing was performed against the [Ignition docker image](https://hub.docker.com/r/kcollins/ignition) built by [Kevin Collins](https://github.com/thirdgen88).
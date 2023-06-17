
Systemd is a system and service manager for Linux operating systems. It is designed to replace the traditional init system and provides a range of features and capabilities for managing system processes, services, and resources.

The `systemctl` command is a powerful utility used for controlling and managing services in Linux distributions that utilize the systemd init system. Here are some common use cases of the `systemctl` command:

You can use `systemctl` to start, stop, restart, reload, enable, disable, or check the status of services. Examples include:

   - Starting a service:
     ```
     sudo systemctl start service_name
     ```

   - Stopping a service:
     ```
     sudo systemctl stop service_name
     ```

   - Restarting a service:
     ```
     sudo systemctl restart service_name
     ```

   - Reloading the configuration of a service without stopping it:
     ```
     sudo systemctl reload service_name
     ```

   - Enabling a service to start on boot:
     ```
     sudo systemctl enable service_name
     ```

   - Disabling a service from starting on boot:
     ```
     sudo systemctl disable service_name
     ```

   - Checking the status of a service:
     ```
     sudo systemctl status service_name
     ```


## Enable

To enable a service to start automatically on boot in Linux, you can use the `systemctl` command. Here's a step-by-step guide:

1. Open a terminal or connect to your Linux system via SSH.

2. Identify the name of the service you want to enable. You can use the `systemctl list-unit-files` command to list all available services and their current status. Look for the service you want to enable and make note of its name.

3. Enable the service using the `systemctl enable` command, followed by the service name. For example, if you want to enable the Apache web server service, the command would be:
   ```
   sudo systemctl enable apache2
   ```

   This command creates the necessary symlinks or configuration files to ensure that the service starts automatically on boot.

4. Verify that the service is enabled by checking its status. Use the `systemctl is-enabled` command, followed by the service name. For example:
   ```
   sudo systemctl is-enabled apache2
   ```

   If the service is enabled, the command will return `enabled`.


*You can use the systemctl list-unit-files command to list all the unit files. They are located in /usr/lib/systemd/system*

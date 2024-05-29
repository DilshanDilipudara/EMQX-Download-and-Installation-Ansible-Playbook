# EMQX Download and Installation Ansible Playbook

This Ansible playbook is designed to automate the download and installation process of EMQX, an MQTT broker, on target systems. It downloads the EMQX binary from a specified URL, verifies the download, and then installs EMQX on the target system.

## Requirements

- Ansible
- Internet access on the target system to download EMQX
- Root or sudo privileges on the target system

## Usage

1. Define the variables:
   - `emqx_version`: Version of EMQX to download.
   - `os_version`: Operating system version.
   - `emqx_download_link`: URL to download the EMQX binary.
   - `emqx_download_path`: Destination path to save the downloaded EMQX binary.
   - `emqx_download_mode`: Permissions mode for the downloaded binary.
   - `emqx_binary_name`: Name of the EMQX binary file.

2. Execute the playbook using the `ansible-playbook` command:



## Playbook Tasks

1. **Download EMQX Binary**: Downloads the EMQX binary from the specified URL to the target system.

2. **Debug EMQX Download Logs**: Displays debug information about the EMQX binary download process.

3. **List Files in Download Path**: Lists the files in the directory where EMQX binary is downloaded.

4. **Debug File List**: Displays debug information about the list of files in the download path.

5. **Install EMQX**: Installs EMQX on the target system using the downloaded binary. It performs the following steps:
- Updates apt repositories.
- Installs `libodbc1`.
- Installs EMQX by running `dpkg -i` with the specified binary file.

6. **Debug Installation Logs**: Displays debug information about the EMQX installation process.


## Playbook Tasks

1. **Download Pushgateway Binary**: Downloads the Pushgateway binary from the specified URL to the target system.

2. **Debug Pushgateway Download Logs**: Displays debug information about the Pushgateway binary download process.

3. **Install Pushgateway**: Installs Pushgateway on the target system by extracting the downloaded binary and copying it to the appropriate directory. It also creates a system user `pushgateway` and sets permissions.

4. **Debug Installation Logs**: Displays debug information about the Pushgateway installation process.

5. **Copy Service File**: Copies the systemd service configuration file from the specified template to `/etc/systemd/system`.

6. **Enable Pushgateway Service**: Enables the Pushgateway service to start automatically on system boot.

7. **Start Pushgateway Service**: Starts the Pushgateway service.


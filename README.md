# Proxmox Ubuntu Installer

This repository packages a helper script that provisions a cloud-init ready Ubuntu virtual machine on **Proxmox VE 9.0.3** (and Proxmox VE 8.1 or newer).

## Prerequisites

* A Proxmox VE node running version 9.0.3 (tested) or any 8.1+ release.
* An `amd64` host with internet access so the script can download Ubuntu cloud images.
* Access to the Proxmox shell (direct console recommended instead of SSH).

## Usage

1. Copy `ubuntu-installer.sh` to your Proxmox host, then make it executable:
   ```bash
   chmod +x ubuntu-installer.sh
   ```
2. Run the script as `root` from the Proxmox shell:
   ```bash
   ./ubuntu-installer.sh
   ```
3. Choose the Ubuntu release you want to deploy. You can accept the default VM configuration or select **Advanced** to customize CPU, RAM, disk size, networking, and auto-start settings.
4. When prompted, pick the target storage where the VM disks should be stored. The script downloads the matching Ubuntu cloud image if it is not already cached, creates the VM, and optionally boots it when the build is complete.

## Post-installation

The created VM is cloud-init ready. Configure cloud-init networking and user data in the Proxmox UI before booting if you did not enable the auto-start option.

## Support

The script originates from the Community Scripts project. Please open issues or discussions in the upstream repository if you encounter problems:
<https://github.com/community-scripts/ProxmoxVE>

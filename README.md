# packer-builds
VM template builds using Hashicorp Packer.

All builds are currently only targeted for deployment to Proxmox. The general goals of these builds are simple:
1. Repeatable VM template creation from a source ISO.
2. Install the guest agent for the target hypervisor.
3. Ensure that OS updates have been applied.

There are currently a couple of issues:
- The Ubuntu 2204 build doesn't apply a static IP until after the first reboot after provisioning a VM from the template.
- The Windows Server 2022 build doesn't create the user and set that users password when provisioning a VM from the template. This might be a issue specifically with using Cloudbase-Init with Proxmox.
- The Windows Server 2022 build requires a password reset for the Administrator account at first logon.
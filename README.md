*This project has been created as part of the 42 curriculum by jcascale.*

# BORN2BEROOT

## DESCRIPTION
Born2beroot is the first system administration project in the 42 curriculum. It requires the creation of a virtual machine using specific strict rules. The goal is to introduce the basics of virtualization, system administration, and security.

We are required to set up a server ensuring specific partitioning (LVM), strict password policies, firewall configuration (UFW), SSH implementation, and a monitoring script. This project is a deep dive into the command line and the "under the hood" operation of a Linux OS.

## Project Description & Design Choices

### Operating System: Debian
For this project, I chose **Debian** (stable) over Rocky Linux.
* **Why Debian?** Debian is known for its stability and its huge community support. It uses `apt` (Advanced Package Tool) and `.deb` packages, which are widely documented. It is the "mother" of popular distros like Ubuntu, making it an excellent starting point for learning Linux structure.
* **Design Choices:**
    * **Partitioning:** I implemented **LVM (Logical Volume Manager)** to allow flexible resizing of partitions. The structure includes encrypted partitions to ensure data security.
    * **Security:** Strict `sudo` policies were implemented to limit root access. **SSH** is configured on port 4242 with root login disabled.
    * **User Management:** Password policies are enforced using `libpam-pwquality` to prevent weak credentials.

### Technical Comparisons

#### Debian vs Rocky Linux
* **Debian:** Uses the Linux kernel and GNU tools. It relies on `apt` and `.deb` packages. It is community-driven and prioritizes stability and free software.
* **Rocky Linux:** A downstream binary compatible clone of RHEL (Red Hat Enterprise Linux). It uses `dnf`/`yum` and `.rpm` packages. It is aimed at enterprise environments requiring RHEL compatibility without the subscription cost.

#### AppArmor vs SELinux
* **AppArmor (used in Debian):** Uses a path-based approach. Profiles are attached to specific executables. It is generally considered easier to learn and configure for beginners.
* **SELinux (used in Rocky/RHEL):** Uses a labeling system (inode-based). Every file and process has a label/context. It is extremely granular and secure but has a steeper learning curve.

#### UFW vs Firewalld
* **UFW (Uncomplicated Firewall):** A frontend for `iptables` designed to be easy to use. It is the standard on Debian/Ubuntu systems. Perfect for simple host-based firewalls.
* **Firewalld:** A dynamic firewall manager with support for network/firewall zones. It allows changing settings without restarting the firewall daemon (standard on RHEL/Rocky).

#### VirtualBox vs UTM
* **VirtualBox:** An open-source hypervisor for x86 architecture. It is the industry standard for desktop virtualization on Windows, Linux, and Intel Macs.
* **UTM:** A virtualization software for macOS (specifically optimized for Apple Silicon M1/M2/M3 chips) that uses QEMU under the hood to emulate or virtualize different architectures.

## Instructions

### Installation
This project consists of a Virtual Machine image (signature verification required).
1.  Download the `.vdi` (VirtualBox) or `.utm` file.
2.  Import the machine into your virtualization software.
3.  Verify the signature (`shasum`) matches the one provided in the submission file `signature.txt`.

### Execution
1.  Start the Virtual Machine.
2.  Log in with the created users.
3.  To connect via SSH from your host terminal:
    ```bash
    ssh <username>@<VM_IP> -p 4242
    ```

## Resources

### Documentation
* [Debian Administrator's Handbook](https://debian-handbook.info/)
* [Sudo Manual](https://www.sudo.ws/man/1.8.13/sudo.man.html)
* [UFW Essentials](https://www.digitalocean.com/community/tutorials/how-to-setup-a-firewall-with-ufw-on-an-ubuntu-and-debian-cloud-server)

### AI Usage
*In accordance with the project guidelines, AI tools were used in the following capacity:*
* **Concept Explanation:** AI was used to understand the differences between AppArmor and SELinux, and to clarify the functioning of LVM partitioning.
* **Scripting Assistance:** AI was consulted to optimize the `monitoring.sh` script, specifically for extracting CPU load and formatted memory usage.
* **Proofreading:** AI was used to check the clarity of the English text in this README and code comments.
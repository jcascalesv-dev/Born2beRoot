*This project has been created as part of the 42 curriculum by jcascale.*

# BORN2BEROOT

## DESCRIPTION
Born2beroot is the first system administration project in the 42 curriculum. It requires the creation of a virtual machine using specific strict rules. The goal is to introduce the basics of virtualization, system administration, and security.

We are required to set up a server ensuring specific partitioning (LVM), strict password policies, firewall configuration (UFW), SSH implementation, and a monitoring script. This project is a deep dive into the command line and the "under the hood" operation of a Linux OS.

### Technical Elections

* **Debian:** This is the subject's recommendation and is known for its stability and broad community support.

## INSTRUCTIONS

### Testing signature
1.  Located the `.vdi` in sgoinfre/Born2BeRoot/.
2.  Verify the signature (`shasum`) matches the one provided in the submission file `signature.txt`.

### Execution
1.  Start the Virtual Machine Clone.
2.  Log in with the created users.
3.  To connect via SSH from your host terminal:
    ```bash
    ssh <username>@localhost -p 4241
    ```

## Resources
- The official project statement (en.subject.pdf).
- Information retrieved through a web browser.
- Peer-to-peer.

### AI Usage
During the development and debugging of this project, AI-based assistance was used to:
- Generate documentation (README.md).
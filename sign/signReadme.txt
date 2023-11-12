This document is specifically designed for enrolling the public key in all the system where installation of QUD driver is required.
When Secure Boot is enabled, all kernel modules must be signed with a private key and authenticated with the corresponding public key.

Step 1 -

Enrolling public key on target system by adding the public key to the MOK list.

Please execute below command -

sudo mokutil --import /opt/QTI/sign/Signkey_pub.der

You will be asked to enter and confirm a password for this MOK enrollment request.
Reboot the machine. At boot time, choose "Enroll MOK" and enter the password that chosen in above step.

Step 2 -

After reboot, verify the information about the public keys on system keyrings by using below command -
sudo keyctl list %:.platform
If \"hostname signing key : ***********************************\" is not present then re-do steps 1.

Step 3 -

Now, public keys becomes permanent part of UEFI Secure Boot key database.
Please try again to install QUD driver from qpm server. Now signing and insertion of modules will be taken care by installer itself.
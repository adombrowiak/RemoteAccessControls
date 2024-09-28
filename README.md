<h1>Remote Access Controls</h1>

[Project 1: Remote Access Controls](https://github.com/user-attachments/files/17102227/dombrowiak_CST620_Project1.pdf)

<h2>Description</h2>
Exploring built-in protective controls inside the Windows OS and Linux OS.


<h2>Tools Utilized</h2>

- <b>Computer Management</b> 
- <b>Remote Desktop Connection</b>
- <b>Windows Firewall</b>
- <b>Mate Terminal</b>

<h2>Environments Used </h2>

- <b>Windows 10</b>
- <b>Kali Linux</b>

<h2>Project Documentation</h2>
<h3>Remote Desktop Protocol Best Practices</h3>
To safeguard against ongoing risks, organizations should prioritize understanding RDP functionality and adopting best practices for its security. These practices include enforcing strong passwords, implementing two-factor authentication, and enabling account lockout policies to thwart brute-force attacks. Additionally, it's crucial to regularly update RDP software and prioritize patching known vulnerabilities with public exploits (Cobb, 2020).</br>
Cost-effective measures such as changing the default RDP port, restricting access to trusted IP addresses, and utilizing VPNs for secure remote access are recommended. Monitoring RDP usage for abnormal behavior, enforcing the principle of least privilege, and using an RDP gateway server for centralized management are further steps to enhance security. Finally, organizations should never expose RDP directly to the internet and regularly scan for any exposed instances, even on non-Microsoft operating systems, to ensure comprehensive protection against potential threats (Cobb, 2020).
</br>
<h3>Secure Shell Best Practices</h3>
Five SSH best practices to enhance security in remote access environments are configuring second-factor authentication, changing the default options, authenticating clients using SSH certificates, using a bastion host, and implementing firewalls. 
Configuring second-factor authentication requires two forms of authentication, like a passphrase and a one-time password. While vulnerable to MITM attacks, any second factor enhances security, with options like YubiKey and Apple TouchID being safer. Enabling 2FA for SSH ensures users need more than one credential, boosting security against theft. Given SSH's common use for secure remote connections, setting up 2FA is crucial for comprehensive protection (Blake, 2022).</br>
	In SSH configuration (/etc/ssh/sshd_config), changing defaults is key for security. Alter the port from 22 to deter attackers and disable root login to limit system access. Shift from password-based to SSH key authentication for better security, and consider SSH certificates for stronger identity verification. Use "AllowUsers" to control SSH access and configure certificate-based authentication via SSH-keygen for enhanced security (Blake, 2022).</br>
A bastion host, situated on a public network and designed to withstand malicious traffic, serves as the initial point of contact before the firewall, shielding systems behind it. Typically hosting a single application and limited services to minimize risk, bastion hosts are widely known online, making their security paramount. Establishing a bastion host can enhance system security, especially in SSH connections (Blake, 2022).</br>
A firewall inspects incoming and outgoing traffic using predefined rules, thereby enhancing server security by controlling traffic flow. Linux system administrators utilize iptables, an interface to the netfilter firewall, to accept or reject packets and safeguard systems from attacks. With iptables, administrators can define rules to permit incoming SSH traffic from trusted sources based on IP address, port, or protocol and track recent SSH port connections. Additionally, they can employ rate-limiting techniques to block IP addresses based on connection frequency, effectively reducing the risk of SSH attacks. Implementing firewall configurations, such as port knocking, further strengthens security by making it challenging to detect open SSH ports (Blake, 2022).</br>
<h3>Remote Desktop Protocol Control Implementation and Testing</h3>
<h4>RDP Findings</h4>

Creating a user with computer management.
![image](https://github.com/user-attachments/assets/b21c0bf6-24b0-4ef7-ab02-3235cbca3603)

Connecting to the 'localhost' using Remote Desktop Connection.
![image](https://github.com/user-attachments/assets/25c543ea-9e96-4ee7-9ed1-e29dd77c7973)

Removing 'Student1' from the Remote Desktop Users.
![image](https://github.com/user-attachments/assets/8236328d-a4a1-4276-ac4d-65a32829c294)

Showing that I cannot connect to 'localhost' with 'Student1'
![image](https://github.com/user-attachments/assets/98c4216a-4f7d-4d96-9146-d38f44b23920)

<h4>Firewall Review with Windwows Firewall</h4>

Reviewing the properties of ‘OpenSSH SSH Server’ and adding the IP address of my Linux VM.
![image](https://github.com/user-attachments/assets/bbc61939-2675-4dcd-9424-0c2294c92c75)

Connecting to SSH via Mate Terminal on Kali.
![image](https://github.com/user-attachments/assets/8c3a561a-406f-4a72-8491-f9d0ab7d2afa)

Connecting to ‘Student 1’ from SSH.
![image](https://github.com/user-attachments/assets/0f96a708-1486-4101-982b-015280a940e6)

Replacing my Kali IP with the IP address 10.10.10.10.
![image](https://github.com/user-attachments/assets/0363aab1-912c-4298-916f-ab0edf6101ca)

Showing that from Kali I am unable to gain access via SSH to ‘Administrator’ and ‘Student1’.
![image](https://github.com/user-attachments/assets/b9af5417-775a-4ac1-8d21-cb1b9d58628a)

<h3>Secure Shell Control Implementation and Testing</h3>
<h4>SSH Findings</h4>

Connecting to Kali using Powershell
![image](https://github.com/user-attachments/assets/bcec47c4-81d3-47c0-8012-1a7d83c0e907)
Both ‘PermitRootLogin’ and ‘PasswordAuthentication’ are set to yes, and as seen above both were already set to yes before I opened ‘/etc/ssh/sshd_config’.
![image](https://github.com/user-attachments/assets/d1ad4e8d-cc0b-4bee-b6ed-47bea9dde65f)
![image](https://github.com/user-attachments/assets/0561f162-6b2b-479f-a5ba-6ab490f7cbd0)

Adding 'Student1' to Kali via SSH connection on the Windows VM.
![image](https://github.com/user-attachments/assets/92c6cc33-18ce-49d0-a911-7995218a7379)

<h4>IPTables Findings</h4>

Reviewing the iptables before removing any connection to port 22, I then inputted the command to drop all connections to port 22. Once the command was run, I reran the iptables command and it showed less information than before.
![image](https://github.com/user-attachments/assets/87f3d2e4-4114-46d0-9b89-c33047b136a6)

After dropping all port 22 connections, I am now unable to connect to Kali through Powershell on PowerShell.
![image](https://github.com/user-attachments/assets/b4eb8451-157e-43be-b062-0b1635c20d68)

I removed the dropped command with ‘sudo iptables -D INPUT 1’.
![image](https://github.com/user-attachments/assets/fede7e73-8cf3-4df6-8296-ba9a57f2f37f)

Since removing the previous command I am now able to connect to Kali via PowerShell. 
![image](https://github.com/user-attachments/assets/e8fd6fa5-335d-464f-b78f-8e80249187c5)

<h4>References</h4>
Blake, C. (2022, April 11). 5 Best Practices for Securing SSH. Teleport. https://goteleport.com/blog/5-ssh-best-practices/
Cobb, M. (2020, August 18). 10 RDP Security Best Practices to Prevent Cyberattacks. TechTarget | Security. https://www.techtarget.com/searchsecurity/tip/10-RDP-security-best-practices-to-prevent-cyberattacks





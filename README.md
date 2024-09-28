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
![Creating a user with computer management](https://github.com/user-attachments/assets/77777fb9-ab2e-4eb1-bc5d-a55d83ab51e1)

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>

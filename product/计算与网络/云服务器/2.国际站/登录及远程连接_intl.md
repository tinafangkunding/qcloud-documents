
### How do I log in to a CVM?

See the following documents:

- [Logging in to a Linux Instance](https://cloud.tencent.com/document/product/213/5436)
- [Logging in to a Windows Instance](https://cloud.tencent.com/document/product/213/5435)

### How do I set the initial password?

When purchasing a CVM, you can set a custom password or use the password automatically generated by the system.

#### Setting a custom password

1. When you [create an instance](https://cloud.tencent.com/doc/product/213/4855), select the login method in the section for setting instance name and login method. It is **Set Password** by default.

2. Enter a password as required by the password character limits and confirm it. Confirm the configuration information, and then click **Buy Now**. After the CVM instance is assigned successfully, log in to the instance using the password you set.

#### Auto-generated password

You can also select **Auto Generated Password** and then click **Buy Now**. After the CVM instance is assigned successfully, you can obtain the initial password in [Internal Message](https://console.cloud.tencent.com/message).

> **Note:**
> The character limits for password:
>   - Linux CVM: The password should be a combination of 8-16 characters comprised of at least two of the following types: ```a-z, A-Z, 0-9 and ( ) ` ~ ! @ # $ % ^ & * - + = _ | { } [ ] : ; ' < > , . ? /``` .
>   - Windows  CVM: The password should be a combination of 12-16 characters comprised of at least three of the following types: ```a-z, A-Z, 0-9 and ( ) ` ~ ! @ # $ % ^ & * - + = _ | { } [ ] : ; ' < > , . ? /```.

### How do I reset the password? What to do if I fail to reset the password?

#### Resetting password

> **Note:**
>
> You can only reset the password if the CVM is in a shutdown status. If the CVM is running, shut down the CVM first.

1. Log in to the [CVM Console](https://console.cloud.tencent.com/cvm/).
2. Reset the password. For an instance whose password cannot be reset, the reason why the password cannot be reset will be displayed.
   1. For a single instance that has been shut down, click **More** -> **Reset Password** in the **Operation** column in the right.
   2. For multiple instances that have been shut down in batch, select all the CVMs whose passwords are to be reset, and then click **Reset Password** at the top of list to modify the login passwords in batch.
3. Enter and confirm the new password, enter the verification code in the **Reset Password** pop-up window, and then click **Confirm Reset**.
4. After the reset is successful, you will receive an internal message indicating the successful reset. Then you can start the CVM using the new password.

#### Failure to reset password

If you cannot reset password even if you're sure that your instance has been shut down, [submit a ticket](https://console.cloud.tencent.com/workorder/category) to contact us.

### When the Linux instance is associated with an SSH key, I failed to log in to the instance with user name and password - What should I do?
After the CVM is associated with an SSH key, login by user name and password is **disabled by default** for the SSH service. Use the SSH key instead to log in to the CVM. 

Please see [Logging in to a Linux Instance](https://cloud.tencent.com/document/product/213/5436)

### What to do if I failed to log in to a Linux instance with an SSH key?

The solutions are as follows:

1. Cancel or modify the security group policy on the [Console](https://console.cloud.tencent.com/cvm/securitygroup). See [Security Group Operation Guide](https://cloud.tencent.com/document/product/213/12450)

2. Cancel "login by key" on the [Console](https://console.cloud.tencent.com/cvm/sshkey) or set "login through key authentication" as instructed. See [SSH Key Operation Guide](https://cloud.tencent.com/document/product/213/16691)

3. Log in to the instance via VNC to check whether the ENI status and IP configuration information are correct. See [Logging in to a Linux Instance](https://cloud.tencent.com/document/product/213/5436)

   ![](https://main.qcloudimg.com/raw/17fa30409db52577fc8fed99a43264d2.png)

4. Verify whether the instance is running normally in Mode 3 or Mode 5:
   ![](https://main.qcloudimg.com/raw/0371d6b8c5a0b89ac70cff6b56adf3be.png)

5. Verify whether the sshd service of the server is running normally and there is no problem with the configuration such as port.
   ![](https://main.qcloudimg.com/raw/32364a0beac01cc63c82d61ebadf89c2.png)
6. Verify whether the server's iptables firewall has blocked the access and whether its policy is OK.![](https://main.qcloudimg.com/raw/9dbc3baa79c24673e59fb228cc57afad.png)
7. Verify whether the tcp_wrappers of the server has blocked SSH access.
   ![](https://main.qcloudimg.com/raw/76ac9f09b606cbd7f2121f4306ff3bc8.png)

8. Verify whether the user who wants to log in to the server via SSH is blocked by the PAM module (this is a rare case):
   ![](https://main.qcloudimg.com/raw/c7af6184b32867d0eb77cdfe1c362d04.png)

### How do I log in to a CVM via VNC?

Login via VNC is a method Tencent Cloud provides for you to connect to your CVMs through Web browser. If the remote login client is not installed or cannot be used, you can connect to your CVM from VNC to check the CVM status and perform basic CVM management operations with your CVM account. For more information, please see the following documents:

- [Logging in to a Linux Instance](https://cloud.tencent.com/document/product/213/5436)
- [Logging in to a Windows Instance](https://cloud.tencent.com/document/product/213/5435)

### How do I configure multi-user remote login for a Windows server?

A Windows server supports remote login by multiple users at a time. Follow the steps below: 

1. Click **Control Panel** -> **Management Tools** -> **Terminal Services** -> **Terminal Service Configuration**    
2. Right-click the RDP-Tcp connection, and then click **Attribute** -> **Network Adapter** -> **Max Connections**
3. By default, if you do not add the terminal service feature, the maximum number of connections can only be adjusted to 2. Set terminal server authorization mode: Go to **Attribute** -> **General**, **unselect** Restrict Each User to Only One Session. Then multi-user login is enabled. If the setting does not take effect, restart the server and try again.

![](https://main.qcloudimg.com/raw/771ba6c304fea14aa1159073d6f0af0c.png)

### How can I log in to a Windows instance using Remote Desktop Connector from a local Windows PC?

See [Logging in to a Windows Instance](https://cloud.tencent.com/document/product/213/5435#.E6.9C.AC.E5.9C.B0.E4.B8.BA-windows-.E8.AE.A1.E7.AE.97.E6.9C.BA).

### How can I log in to a Windows instance using rdesktop from a local Linux PC?

See [Logging in to a Windows Instance](https://cloud.tencent.com/document/product/213/5435#.E6.9C.AC.E5.9C.B0.E4.B8.BA-linux-.E8.AE.A1.E7.AE.97.E6.9C.BA).

### How can I log in to a Windows instance using Microsoft Remote Desktop Connection Client for Mac from a local Mac OS PC?

See [Logging in to a Windows Instance](https://cloud.tencent.com/document/product/213/5435#.E6.9C.AC.E5.9C.B0.E4.B8.BA-mac-os-.E8.AE.A1.E7.AE.97.E6.9C.BA).

### How can I log in to an instance using root user from a Ubuntu system?

The default user name for Ubuntu system is ubuntu, and the root account and password are not set by default during the installation. If necessary, enable "login with root user" in Settings. Follow the steps below:
1. Modify root password. Enter the following command and enter the password.

  ```
  sudo passwd root
  ```
Root user has no password by default, so it is unavailable. To use the root user, set a password for the root user first.
![](https://main.qcloudimg.com/raw/39577876c773f35904c87538bf18b6fa.png)

2. Modify SSH configuration. Change PermitRootLogin to yes, and then save and exit.
  ```
  sudo vi /etc/ssh/sshd_config 
  ```
  ![](https://main.qcloudimg.com/raw/53180728677a3c4cad46821485e82437.png)

 3. Restart SSH service.
    ```
    sudo service ssh restart
    ```
4. Finally, verify whether you can log in remotely using the root user.

### How do I reset passwords for multiple online Linux instances in batch?

To reset passwords for multiple Linux instances in batch without shutting down the instances, click to download the [script for batch reset](http://batchchpasswd-10016717.file.myqcloud.com/batch-chpasswd.tgz?_ga=1.165307193.726382295.1500898081) and run the script. The script is used as follows:

> **Note:**
> - If you run the script on a public network-based server, the IP entered in the hosts.txt file must be the public IP of the instance.
> - If you run the script on a private network-based server, enter the private IP of the instance.

Enter the IP of the instance to be operated, SSH port, account, and old and new passwords in the hosts.txt file. Each line represents a server, for example:
```
10.0.0.1 22 root old_passwd new_passwd 
10.0.0.2 22 root old_passwd new_passwd
```
Run the following code:
```
./batch-chpasswd.py
```

Response Example:
```
change password for root@10.0.0.1
spawn ssh root@10.0.0.1 -p 22
root's password: 
Authentication successful.
Last login: Tue Nov 17 20:22:25 2017 from 10.181.225.39
[root@VM_18_18_centos ~]# echo root:root | chpasswd
[root@VM_18_18_centos ~]# exit
logout
```

```
change password for root@10.0.0.2
spawn ssh root@10.0.0.2 -p 22
root's password: 
Authentication successful.
Last login: Mon Nov  9 15:19:22 2017 from 10.181.225.39
[root@VM_19_150_centos ~]# echo root:root | chpasswd
[root@VM_19_150_centos ~]# exit
logout
```


# Module 8 – Enhanced Security

<p align="left"><img src="../Images/asc-labs-advanced.gif?raw=true"></p>

#### 🎓 Level: 300 (Advanced)
#### ⌛ Estimated time to complete this lab: 60 minutes

### Exercise 1: Using JIT to reduce attack surface

1.	From Microsoft Defender for Cloud sidebar, click on **Workload Protections**.
2.	On the Advanced protection part at the bottom, click on **Just-in-time VM access** (You should see 2 unprotected status).

![Advanced protection options](../Images/asc-defender-advanced-protection-jit.gif?raw=true)

3.	On the Just-in-time VM access page, select the **Not configure** tab. You should see at least two virtual machines listed: `asclab-linux` and `asclab-win`.
4.	Select **asclab-win** and then click on the **Enable JIT on 1 VM** button.

![Enable JIT on Windows VM](../Images/asc-enable-jit-win-vm.gif?raw=true)

5.	On the JIT VM access configuration, keep just the **3389 (RDP) port** set to **On**, and set all others to **Off**. 

![](../Images/lab8jit.gif?raw=true)
6.	Click **Save** to apply the VM access configuration.

![JIT VM access configuration](../Images/asc-jit-vm-access-config.gif?raw=true)

7.	Review the **Configured** tab, now you should see your VM configured: `asclab-win`.
8.	On the Azure portal sidebar, click on **Virtual Machines**.
9.	Click on **asclab-win**.
10.	From the top menu, click on **Connect** button and then select **RDP**.

![Windows VM - Connect RDP](../Images/asc-win-vm-connect-rdp.gif?raw=true)

11.	Return to the VM blade. On the Connect page, request JIT access. On the **Source IP**, select **My IP** and then click on **Request access**. You should now see the following message: *Download file*.

![](../Images/lab8download.gif?raw=true)
12.	Try to connect again to validate your JIT access to the VM. Use the same file you downloaded previously.
13.	Now you should get the prompt for the local admin credentials. **Type your username and password** and click **OK**.
14.	You **are now connected to asclab-win** server. Close the remote control session/log off.

### Exercise 2: Adaptive Application Control

Application control helps you deal with malicious and/or unauthorized software, by allowing only specific applications to run on your machines.

1.	From Microsoft Defender for Cloud sidebar, click on **Workload Protections**.
2.	On the Advanced protection part at the bottom, click on **Adaptive application control**.

![](../Images/lab8aac.gif?raw=true)
3.	The Adaptive application controls page opens with your VMs grouped into the following tabs: Configured, Recommended and No recommendations.
4.	Click on the **Recommended** tab.
5.	If this tab does not contain any group yet, it means that Microsoft Defender for Cloud needs at least two weeks of data to define the unique recommendations per group of machines.

### Exercise 3: File Integrity Monitoring

File integrity monitoring (FIM), also known as change monitoring, examines operating system files, Windows registries, application software, Linux system files, and more, for changes that might indicate an attack.
It maps the current state of these items with the state during the previous scan and alerts you if suspicious modifications have been made. To enable FIM, follow the instructions below:

1.	From Microsoft Defender for Cloud sidebar, click on **Workload Protections**.
2.	On the Advanced protection part at the bottom, click on **File Integrity Monitoring** tile.
3.	On the FIM configuration page, select the **Log Analytics workspace listed** `asclab-la-xxx` (or just by clicking on the Upgrade icon - it indicates that FIM is not enabled for the selected workspace).
4.	On the Enable FIM, **review the default recommended settings** for Windows files, Registry and Linux files.
5.	Click on **Enable File Integrity Monitoring** button.

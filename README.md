# VBoxWin11
After struggling for over a month trying to get VirtualBox to work on Windows 11 with hardware VTx accelaration I've finallly cracked it, so thought I would write it up to help anyone else facing the same issue.

1. Download Microsoft's Device Guard and Credential Guard hardware readiness tool from the following URL : [https://www.microsoft.com/en-us/download/details.aspx?id=53337]
2. Extract the files from the zip file.
3. Open a PowerShell window and navigate to the folder where you extracted the files.
4. Run the command below, the system will reboot and guide ask you if you want to disable Device Guard and Crdential Guard, you need to answer yes to both by either pressing F3 or the Windows key.
```
.\DG_Readiness_Tool_v3.6.ps1 -Disable -AutoReboot
```
After doing this you should be able to run your VirtalBox VMs with full hardware accelaration.

> [!NOTE]
> If after a reboot the green turle comes back, this means you have a UEFI lock to re-enable the Credential Guard, this page [https://learn.microsoft.com/en-us/windows/security/identity-protection/credential-guard/configure?tabs=intune] has instructions on how to disable this lock but I have not tried them so cannot say if it works.\
> \
> Re-running the command in the instructions above should disable Credential Guard again.

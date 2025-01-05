# Installing .NET Framework 3.5 on Windows Sandbox 24H2

Follow these steps to install .NET Framework 3.5 in a Windows Sandbox environment running version 24H2:

## Instructions

1. Open a PowerShell window with administrative privileges and run the following command to configure Windows Update settings:

    ```powershell
    Set-ItemProperty -Path "HKLM:\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate\AU" -Name "UseWUServer" -Value 0
    ```

2. Restart the Windows Update service by running:

    ```powershell
    Restart-Service wuauserv
    ```

3. Run a DISM command to repair the system image (this process may take some time):

    ```cmd
    dism /online /Cleanup-Image /RestoreHealth
    ```

4. Download and unzip the `NET_Framework_3.5_Windows_10.zip` package.

5. Execute the installer from the unzipped folder and wait for the installation to complete.

---

### Notes
- Ensure you have an active internet connection for the DISM command to work properly.
- Running these commands requires administrative privileges.

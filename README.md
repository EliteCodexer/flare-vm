<pre>
      ______ _               _____  ______   __      ____  __
     |  ____| |        /\   |  __ \|  ____|  \ \    / /  \/  |
     | |__  | |       /  \  | |__) | |__      \ \  / /| \  / |
     |  __| | |      / /\ \ |  _  /|  __|      \ \/ / | |\/| |
     | |    | |____ / ____ \| | \ \| |____      \  /  | |  | |
     |_|    |______/_/    \_\_|  \_\______|      \/   |_|  |_|

      ________________________________________________________
                           Developed by
                       flarevm@mandiant.com
                      FLARE Team at Mandiant
      ________________________________________________________
</pre>

<p align="center">
  <img width="300" height="300" src="flarevm.png?raw=true" alt="FLARE VM"/>
</p>

Welcome to FLARE VM - a collection of software installations scripts for Windows systems that allows you to easily setup and maintain a reverse engineering environment on a virtual machine (VM). FLARE VM was designed to solve the problem of reverse engineering tool curation and relies on two main technologies: [Chocolatey](https://chocolatey.org) and [Boxstarter](https://boxstarter.org). Chocolatey is a Windows-based Nuget package management system, where a "package" is essentially a ZIP file containing PowerShell installation scripts that download and configure a specific tool. Boxstarter leverages Chocolatey packages to automate the installation of software and create repeatable, scripted Windows environments.

Updates
===

Our most recent updates make FLARE VM even more open and maintainable to allow the community to easily add and update tools and make them quickly available to everyone. We've worked hard to open source the packages which detail how to install and configure analysis tools. The FLARE VM project now uses automatic testing, updating, and releasing to make updated packages immediately installable. Read on for more details and all the relevant project and documentation links.

See this [blog](insert URL) for more information regarding changes!

Installation
===

> **Note:** FLARE VM should ONLY be installed on a virtual machine!

* Prepare a Windows 10+ virtual machine
  * FLARE VM has been tested on [Windows 10 1809 x64](https://developer.microsoft.com/en-us/microsoft-edge/tools/vms/)
  * We recommend to avoid usernames that contain a space or other special characters
  * We recommend a disk capacity of at least 70-80 GB and memory of at least 2 GB
  * Disable Windows Updates (at least until installation is finished)
* Disable Tamper Protection and any Anti-Malware solution (especially Windows Defender), preferably via GPO). See below for resource links:
  * Disabling Tamper Protection:
    * https://support.microsoft.com/en-us/windows/prevent-changes-to-security-settings-with-tamper-protection-31d51aaa-645d-408e-6ce7-8d7f8e593f87
    * https://www.tenforums.com/tutorials/123792-turn-off-tamper-protection-windows-defender-antivirus.html
  * Disabling Windows Defender:
    * https://stackoverflow.com/questions/62174426/how-to-permanently-disable-windows-defender-real-time-protection-with-gpo
    * https://www.windowscentral.com/how-permanently-disable-windows-defender-windows-10
    * https://github.com/jeremybeaume/tools/blob/master/disable-defender.ps1
* Take a VM snapshot so you can always revert to a state before FLARE VM installation
* Open a `PowerShell` window as administrator
* Download the the installation script [`installer.ps1`](https://raw.githubusercontent.com/mandiant/flare-vm/master/install.ps1) to your desktop
  * `iex ((New-Object net.webclient).DownloadString('https://raw.githubusercontent.com/mandiant/flare-vm/master/install.ps1'))`
* Unblock the installation script by running:
  * `Unblock-File .\install.ps1`
* Enable script execution by running:
  * `Set-ExecutionPolicy Unrestricted`
* Finally, execute the installer script as follow:
  * `.\install.ps1`
    * You can also pass your password as an argument: `.\install.ps1 -password <password>`
* After installation it is recommended to switch to "host-only" networking mode and take a VM snapshot

Contributing
===
Want to get started contributing? See the links below to learn how.
* FLARE VM installation script and configuration
  * https://github.com/mandiant/flare-vm
* Submit ideas and issues related to the installer script and configuration
  * https://github.com/mandiant/flare-vm/* sues
* Repository of all tool packages
  * https://github.com/mandiant/VM-Packages
* Documentation and contribution guides for tool packages
  * https://github.com/mandiant/VM-Packages/wiki
* Submit new tool packages or report related issues
  * https://github.com/mandiant/VM-Packages/issues

Legal Notice
============
<pre>This download configuration script is provided to assist cyber security analysts
in creating handy and versatile toolboxes for malware analysis environments. It
provides a convenient interface for them to obtain a useful set of analysis
tools directly from their original sources. Installation and use of this script
is subject to the Apache 2.0 License.

You as a user of this script must review, accept and comply with the license
terms of each downloaded/installed package. By proceeding with the
installation, you are accepting the license terms of each package, and
acknowledging that your use of each package will be subject to its respective
license terms.
</pre>


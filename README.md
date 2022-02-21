# Auto-Ays-Restore
**This script creates restore point (binary backup file) and reverts mikrotik to this restore point in a given pediod of time unless user deactivates this script.**

**How to setup an Auto-Ays-Restore script**
1. Download [auto-sys-restore.rsc](https://raw.githubusercontent.com/mikrotik-user/auto-sys-restore/main/auto-sys-restore.rsc) on your mikrotik router `/tool fetch url="https://raw.githubusercontent.com/mikrotik-user/auto-sys-restore/main/auto-sys-restore.rsc" mode=https dst-path=auto-sys-restore.rsc`. Also you may download [file](https://raw.githubusercontent.com/mikrotik-user/auto-sys-restore/main/auto-sys-restore.rsc) manually and upload it to router.
2. Import script `/import auto-sys-restore.rsc`. You may also copy content of [this page](https://raw.githubusercontent.com/mikrotik-user/auto-sys-restore/main/auto-sys-restore.rsc) and paste to a newly created script using GUI.
3. Now you may run this script via CLI. `/system script run auto-sys-restore` or directly from Winbox
4. To disarm `auto-sys-restore` run `no-autosys-restore` script that is generated automatically immediatelly after main script was initiated.

**Usage scenarios**
If you're working on a remote mikrotik router and there's a possibility you can be kicked out from Winbox or CLI by misconfiguring management IP address or firewall rule you shoulr run `auto-sys-restore` script before making any cahnges in configuration. Once script is ran you have 10 minutes to change critical section in configuration. If everything is OK simply disarm restore script by running `no-autosys-restore`

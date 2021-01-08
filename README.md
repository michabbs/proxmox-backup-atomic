# proxmox-backup-atomic

This wrapper script creates backup of a set of ZFS datasets and/or zvols.
All backup sources are snapshotted AT THE SAME TIME and then the snapshots are stored on
Proxmox Backup Server using standard proxmox-backup-client.
You will get either backup of all data or none.

Note: All sources data MUST be placed in the same ZFS pool.
It is impossible to make "atomic" snapshot of more than one ZFS pool.

This script should be run as root (or via sudo, or possibly via sudo -E).
Running as regular user was not tested.

# USAGE:

    proxmox-backup-atomic archivename.pxar:zfspool/dataset archivename.img:zfspool/zvol ...

See configuration variables inside the script.

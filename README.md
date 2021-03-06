libvirt-drbd
============

This script is a libvirt hook to automatically promote/demote DRBD
resources.

Place the "qemu" script in /etc/libvirt/hooks/ and it will
automatically promote and demote DRBD resources configured in libvirt
guests when the guests are started or shut down. After installing it,
the libvirt management daemon needs to be reloaded:

/etc/init.d/libvirt-bin reload

or, on systemd based systems

systemctl restart libvirtd
 
In order for the DRBD resources to be recognized as such, they need to
be configured with the /dev/drbd/by-res/<name> path.
 
The script requires the xmllint command from the libxml package.

The latest version of the script is at
https://github.com/ohitz/libvirt-drbd

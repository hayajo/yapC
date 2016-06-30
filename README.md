yapC
====

yapC - yet another pachimon Container

SYNOPSIS
--------

```sh
sudo yapc /bin/bash
sudo YAPC_CPU_QUOTA=50000 yapc /bin/bash -c "yes >/dev/null"
sudo YAPC_CAP="cap_net_raw" yapc ping 127.0.0.1
sudo YAPC_NET=1 yapc ip link
sudo YAPC_UID=1000 YAPC_GID=1000 yapc id
sudo YAPC_DEBUG=1 yapc date

# docker export $(docker create centos) | tar xC /path/to/centos/rootfs
sudo YAPC_ROOT=/path/to/centos/rootfs yapc yum --help
```

REQUIREMENTS
------------

- Linux Kernel >= 4.3.0
- bash
- util-linux
- cgourp-tools
- libcap >= 2.23
- overlayfs
- iproute2

This project bundle with the `Vagrantfile`.

ENVS
----

### YAPC_ROOT

default: `/`

root directory.

### YAPC_CAPS

default: `cap_chown,cap_dac_override,cap_fsetid,cap_fowner,cap_mknod,cap_setgid,cap_setuid,cap_setfcap,cap_setpcap,cap_net_bind_service,cap_sys_chroot,cap_kill,cap_audit_write`

capabilities.

### YAPC_NAME

default: ''

set `hostname`.

### YAPC_NET

default: ''

isolate Network Namespace.

### YAPC_UID

default: `id -u`(be mostly 1)

USER ID.

### YAPC_GID

default: `id -g`(be mostly 1)

GROUP ID.

### YAPC_CPU_QUOTA

default: ''

set to `cpu.cfs_quota_us`.

### YAPC_MEMORY_LIMIT

default: ''

set to `memory.limit_in_bytes`.

### YAPC_PIDS_MAX

default: ''

set to `pids.max`.

### YAPC_DEBUG

default: ''

`set -x`.


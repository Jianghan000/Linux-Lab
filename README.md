### 以下均为每个实验的运行结果
# 一、MBR 中磁盘分区表解析
```
MBR Partition Table:
Partition 1:
  Bootable: Yes
  Partition Type: 0x83
  Start LBA: 2048
  Partition Size: 83884032 sectors
Partition 2:
  Bootable: No
  Partition Type: 0x00
  Start LBA: 0
  Partition Size: 0 sectors
Partition 3:
  Bootable: No
  Partition Type: 0x00
  Start LBA: 0
  Partition Size: 0 sectors
Partition 4:
  Bootable: No
  Partition Type: 0x00
  Start LBA: 0
  Partition Size: 0 sectors
```
# 二、当前进程页表目录获取
```
Testing with a new virtual address: 0x7faf7c0e5000
Virtual address 0x7faf7c0e5000 is not present in memory
```

# 三、全局描述符表获取
```
全局描述符表（GDT）:
GDT条目 0:
  基地址: 0x00000000
  限长: 0x00010000
  访问权限: 0x00
  粒度标志: 0x00
GDT条目 1:
  基地址: 0x00fdd69a00
  限长: 0x1d790000
  访问权限: 0x7f
  粒度标志: 0x00
GDT条目 2:
  基地址: 0x00000000
  限长: 0x00000000
  访问权限: 0x00
  粒度标志: 0x00
```

# 四、模拟 malloc/free 内存分配与回收
```
mmalloc: 分配内存块 0x4040c0，大小 64 字节
mmalloc: 分配内存块 0x404100，大小 128 字节
mmalloc: 分配内存块 0x404180，大小 512 字节
mfree: 释放内存块 0x404110，大小 128 字节
mmalloc: 分配内存块 0x404100，大小 32 字节
mfree: 释放内存块 0x4040d0，大小 64 字节
mfree: 释放内存块 0x404190，大小 512 字节
mfree: 释放内存块 0x404110，大小 32 字节
```

# 五、访问所有任务（进程）
```
systemd
kthreadd
rcu_gp
rcu_par_gp
kworker/0:0H-kblockd
mm_percpu_wq
ksoftirqd/0
rcu_sched
rcu_bh
migration/0
cpuhp/0
kdevtmpfs
netns
kauditd
khungtaskd
oom_reaper
writeback
kcompactd0
ksmd
khugepaged
crypto
kintegrityd
kblockd
md
edac-poller
watchdogd
kswapd0
kthrotld
acpi_thermal_pm
kmpath_rdacd
kaluad
ipv6_addrconf
kstrp
ata_sff
scsi_eh_0
scsi_eh_1
scsi_tmf_0
scsi_tmf_1
scsi_eh_2
scsi_tmf_2
scsi_eh_3
scsi_tmf_3
kworker/0:1H-kblockd
scsi_eh_4
scsi_tmf_4
scsi_eh_5
scsi_tmf_5
scsi_eh_6
scsi_tmf_6
scsi_eh_7
scsi_tmf_7
scsi_eh_8
scsi_tmf_8
scsi_eh_9
scsi_tmf_9
jbd2/vda1-8
ext4-rsv-conver
systemd-journal
systemd-udevd
auditd
dbus-daemon
NetworkManager
chronyd
polkitd
rngd
rsyslogd
systemd-network
systemd-logind
tuned
ttm_swap
dhclient
wrapper
java
crond
agetty
agetty
sshd
hostwatch
hostguard
containerserver
sshd
systemd
(sd-pam)
sshd
bash
kworker/u2:2-events_unbound
kworker/0:0-cgroup_pidlist_destroy
kworker/u2:1-events_unbound
kworker/0:1-events_power_efficient
l6.out
```

# 六、文件缓冲区设计
```
Disk read: Offset = 0, Length = 4096 bytes
Accessed data at offset 0:
Disk write: Offset = 0, Length = 4096 bytes
Disk read: Offset = 4096, Length = 4096 bytes
Accessed data at offset 4096:
Disk write: Offset = 4096, Length = 4096 bytes
Disk read: Offset = 8192, Length = 4096 bytes
Accessed data at offset 8192:
Disk write: Offset = 8192, Length = 4096 bytes
```

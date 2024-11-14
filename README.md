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

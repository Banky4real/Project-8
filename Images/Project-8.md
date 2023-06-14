## **Documentation for Project 8**

### Entire View of partitioned Volume 
`lsblk`
![list-of-newly-partitioned-volume](./Images-NFS-Server/Partitioned-volume-view.png)

### LVM2 Installation
`sudo yum install lvm2`
![lVM2-Installation](./Images-NFS-Server/LVM-2-Installed.png)

### Partition Marked as Physical Volume
`sudo pvcreate /dev/xvdf1`
`sudo pvcreate /dev/xvdg1`
`sudo pvcreate /dev/xvdh1`
`sudo pvs`
![Marking-partition-as-physical-Volume](./Images-NFS-Server/Partitons-marked-as-physical-volumes.png)

### Creating a Volume Group
`sudo vgcreate webdata-vg /dev/xvdh1 /dev/xvdg1 /dev/xvdf1`
`sudo vgs`
![Volume-Group-Creation](./Images-NFS-Server/Volume-group-created.png)

### Creating Logical Volume
`sudo lvcreate -n lv-apps -L 9G webdata-vg`
`sudo lvcreate -n lv-logs -L 9G webdata-vg`
`sudo lvcreate -n lv-opt -L 9G webdata-vg`
`sudo lvs`
![Logical-Volume-Creation](./Images-NFS-Server/Logical-volumes-created.png)
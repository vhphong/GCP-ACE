# Local SSD
- Block Level storage
- Very fast hard drives physically attached to the server
- Data is deleted when instance is stopped or deleted
- 375 GB solid state drives
- Can attach a maximum of 24 local SSD partitions for a total of 9TB per instance (Amount of partitions that can be attached depends on the machine type)
- good for stateless workloads
- Local SSD storage isn't automatically replicated and **all data on the local SSD might be lost** if the instance terminates for any reason.

# Persistent Disk
- Block level Storage
- Like a physically attached SSD in terms of interfacing purposes
- However it is attached to an instance via a network attachment
- Much slower than a local SSD but fast enough for most users
- Performance scales automatically with size, so you can resize or add more as needed
- Persistent disks are not deleted with the instance
- Persistent disks can be used to make snapshots
- Persistent disks are reattachable to different instances

# Cloud Filestore
- File Level Storage
- Fully managed file based storage system
- Network attached storage
- Scales to meet needs of high performance workloads
- Makes data and metdata backups easy
- A single filestore can be used by many computers
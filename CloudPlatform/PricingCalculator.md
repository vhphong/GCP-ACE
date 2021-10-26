# Pricing Calculator

# GCE - Compute Engine
- CPUs
- memory
- GPUs
- OS
- Persistent disks
- unused Static IPs

# GCS - Cloud Storage
- Data storage amount - Storage rates vary depending on the storage class of your data and location of your buckets.
- Network Usage - the amount of data read from or moved between your buckets.
- Operations usage - the actions you take in Cloud Storage, such as listing the objects in your buckets.
- Retrieval and early deletion fees - applicable for data stored in the Nearline Storage, Coldline Storage, and Archive Storage classes.
- storage class
    - Also data retrieval size if not standard GCS
    - Nearline and coldline have minimum durations
- Class A Operations
    - writes updates
- Class B Operations
    - read
- Pay more for multi-regional buckets than regional buckets

# Bigtable 
- When you use Bigtable, you are charged for the following:
    - The type of Bigtable instance and the total number of nodes in your instance's clusters.
    - The amount of storage that your tables use.
    - The amount of network bandwidth that you use.
- Pay for the nodes you use

# GKE - Kubernetes Engine
- GPUs
- LoadBalancers
- nodes
- Machine type

# Cloud Functions
- pricing
    - Cloud Functions are priced according to how long your function runs, how many times it's invoked and how many resources you provision for the function. If your function makes an outbound network request, there are also additional data transfer fees. 
    - Cloud Functions includes a perpetual free tier for invocations to allow you to experiment with the platform at no charge. 
- Execution Time
- Invocations
    - default 1000 invocations/second
- Bandwith
- Type
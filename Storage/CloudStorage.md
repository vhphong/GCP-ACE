# GCS: Google Cloud Storage
- Primary service for storing files/**objects**
    - Additional examples:
        - blob (binary large object)
        - JPGs,PNGs,PDFs,TXTs,HTMLs
    - **Multi-regional**: are designed to be able to function following the loss of a single region.
    - Analogous to S3 for AWS
    - Objects are atomic units: It cannot edit or read just part of an object
    - Objects can be versioned
        - Lastest version is called the **live version**
    - Additional highlights: 
        - https://cloud.google.com/files/CloudStorage.pdf


- Pricing:
    - Pricing is based on **what you use**, including the **amount of data you store**, the **duration for which you store it**, the **number of operations you perform on your data**, and the **network resources used** when moving or accessing your data.
    - Storage and bandwidth usage are calculated in gigabytes (GB),
    where 1 GB = 230 bytes. 


- **Buckets** are a collection of objects
    - Bucket names must be gloablly unique
    - Files are private by default 
    - Uniquely named across **ALL GCP** accounts created by everyone

- **Bucket Permissions**
    - **Uniform**: All objects in the bucket have the same permission level 
    - **Fine Grained**: You can set permission levels per object

- To make files public, you have to edit persmissions
    - Add entity Group
    - Name allUsers
- Many other services like AppEngine use GCS
- **Buckets must be made for a geographic location**
    - **Multi-region**
        - example: United States
    - **Dual-region**
        - examples: Iowa and South Carolina
    - **Region**
        - example: Europe-north1
- Pick a location geographically near the resources that will be using it.
- Buckets locations cannot be edited once created.
    - To "edit" you should make a new bucket in the correct location.
- **Static Website Hosting**: Putting the HTML/CSS/JS into a bucket and making the files public

    
- **Storage Classes for any workload**
    - Buckets can be created for different storage accessiblity
    - Done to save money for less accessed files
    - You can start with a class that matches your current use, then reconfigure for cost savings.
    - All classes have a minium storage duration which is how long it must be in the bucket before being accessed *without* a cost penalty
    - All objects in storage are accessible in milleseconds *for a price*
    - In general you pay more for data transfer and less for data storage
    - **Types**:
        - **Standard**: good for data accessed frequently. This includes websites, streaming videos, and mobile apps.
        - **Nearline**: *LOW COST* and good for data that can be stored for **AT LEAST 30 days.** This includes data backup and long-tail multi-media content. 
        - **Coldline**: *VERY LOW COST* and good for data that can be stored for **AT LEAST 90 days.**
        - **Archive**: ***LOWEST COST*** and good for data that can be stored for **AT LEAST 365 days, including regulatory archives.**


## CLI Command
- **gsutil** is the tool for GCS commands
    - You can use **gsutil** to do a wide range of bucket and object management tasks, including:

### Create a Bucket
```bash
    gsutil mb gs://bucket-name
```

### List all buckets in project
```bash
    gsutil list
```

### List objects in bucket 
```bash
    gsutil list gs://bucketname
```
### Upload
```bash
    gsutil cp localfile gs://bucketname
```

### Download
```bash
    gsutil cp gs://bucketname/something.txt .
```

### Permissions (Access Control list )
```bash
    gsutil acl set 
    gsutil acl ch 
    gsutil acl get
    gsutil acl ch -u AllUsers:r gs://wassup/cheatsheet.png
    
```

#### Get metadata
```bash
    gsutil stat gs://bucketname/object
```

```bash
    gsutil rewrite -s coldline gs://mybucket/something.txt
```
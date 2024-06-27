# Benchmarks

The following section provides some performance figures for CleverDocs's CPU and GPU pipelines/containers on various AWS instance types

## PDF de-identification

For evaluation, we are used 3 PDF documents with total number of pages is 410 which contain scanned documents.

Please look more detail about performance of `CleverDoc` in related blog post: [Automated PDF de-identification: Performance Analysis](https://medium.com/@apicom.pro/automated-pdf-de-identification-performance-analysis-672132f74233)

### CPU


| Instance Type | vCPUs | Memory<br/> (GiB) | Price<br/> ($/hour) | Throughput<br/> (pages/sec) | Latency for 410<br/> pages request (secs) |
|---------------|-------|--------------|----------------|-----------------------------|--------------------------------------|
|[m6g.8xlarge](https://instances.vantage.sh/aws/ec2/m6g.8xlarge)               | 32    | 128          |   $1.232             | 4.4                         | 98                                   |

### GPU


| Instance Type | vCPUs | GPUs | Memory<br/> (GiB) | GPU Memory<br/> (GiB) | Price<br/> ($/hour) | Throughput<br/> (pages/sec) | Latency for 410<br/> pages request (secs) |
|---------------|-------|------|--------------|------------------|----------------|-----------------------------|--------------------------------------|
|[g4dn.8xlarge](https://instances.vantage.sh/aws/ec2/g4dn.8xlarge)               | 32    | 1    | 128          | 16               |   $2.176             | 7.4                         | 55                                   |


## Image de-identification

Dataset: 
 - 100 PNG images of scanned documents with text
 - Resolution: 300 dpi
 - Width: 2469 px
 - Height: 3500 px

### CPU


| Instance Type | vCPUs | Memory<br/> (GiB) | Price<br/> ($/hour) | Throughput<br/> (images/sec) | Latency for 100 images request (secs) |
|---------------|-------|--------------|----------------|------------------------------|---------------------------------------|
|[m6g.8xlarge](https://instances.vantage.sh/aws/ec2/m6g.8xlarge)               | 32    | 128          |   $1.232             | 6.8                          | 14.5                                  |


### GPU


| Instance Type | vCPUs | GPUs | Memory<br/> (GiB) | GPU Memory<br/> (GIB) | Price<br/> ($/hour) | Throughput<br/> (images/sec) | Latency for 100<br/> images request (secs) |
|---------------|-------|------|--------------|------------------|----------------|------------------------------|---------------------------------------|
|[g4dn.8xlarge](https://instances.vantage.sh/aws/ec2/g4dn.8xlarge)               | 32    | 1    | 128          | 16               |   $2.176             | 9                            | 11                                    |

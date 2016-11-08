---
services: Blob-Storage
platforms: .Net
author: msonecode
---

# List the blobs in a container with the specified prefix

##Introduction
<br/>
This is an example of how to list the blobs in a container whose names begin with the specified prefix.
The ListBlobs method lists blobs and virtual directories in a container, optionally in segments of a specified or default size.
You can optionally specify a blob prefix to list blobs whose names begin with the same string. If you use a delimiter character in your blob names to create a virtual directory structure, the blob prefix can include all or part of the virtual directory structure (but not the container name).
You can list blobs hierarchically, in a manner similar to traversing a file system, or in a flat listing, where all blobs matching the specified prefix are returned by the listing operation.
You can specify additional details to return with the listing, including copy properties, metadata, snapshots, and uncommitted blobs.

## Prerequisites

***1. Azure Account***
<br/>
You need an Azure account. You can [open a free Azure account](https://azure.microsoft.com/pricing/free-trial/?WT.mc_id=A261C142F) or [Activate Visual Studio subscriber benefits](https://azure.microsoft.com/pricing/member-offers/msdn-benefits-details/?WT.mc_id=A261C142F).

***2. Visual Studio 2015***
<br/>
https://www.visualstudio.com/downloads/

***3. Azure SDK***
<br/>
The tutorial is written for Visual Studio 2015 with the [Azure SDK for .NET 2.9](https://azure.microsoft.com/en-us/documentation/articles/dotnet-sdk/) or later.
[Download the latest Azure SDK for Visual Studio 2015](http://go.microsoft.com/fwlink/?linkid=518003). The SDK installs Visual Studio 2015 if you don't already have it.

## Run the sample
Before you build the solution, please do some modification as below:<br/>
Please note delete operation  cannot undo. So make sure you have confirmed the code logic first.<br/>
1.	Enter your storage account name, account key and container name as below lines.<br/>
<img src="https://github.com/zhangdingsong/ListBlobsWithinContainer/blob/master/1.png"><br/>
2.	Please specified your prefix if needed to meet your demands, and enable line 46 when you needed to remove those blobs.<br/>
<img src="https://github.com/zhangdingsong/ListBlobsWithinContainer/blob/master/2.png"><br/>
3.  Add a threshold parameter for method ListBlobsFromContainer().
```csharp
var rsltList = ListBlobsFromContainer(container, prefix, 5000);

private static List<Uri> ListBlobsFromContainer(CloudBlobContainer container, string prefix, int threshold)

if (lstBlobUri.Count > threshold)
{
  break;
}
```
lll
```c#
var rsltList = ListBlobsFromContainer(container, prefix, 5000);

private static List<Uri> ListBlobsFromContainer(CloudBlobContainer container, string prefix, int threshold)

if (lstBlobUri.Count > threshold)
{
  break;
}
```

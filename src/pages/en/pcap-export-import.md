---
title: PCAP-based Workflow
description: With its distributed PCA-based architecture, optimized for performance and scale, Kubeshark makes PCAP or It Didn't Happen possible.
layout: ../../layouts/MainLayout.astro
mascot:
---
**Optimized for Performance and Scale**

## Distributed PCAP-based Storage

**Kubeshark**’s workers store the captured TCP streams in the root file system of each node in the cluster as separate PCAP files.
It also keeps track of name resolution history with a JSON dump. This PCAP-based workflow enables a seamless exporting and importing
capability of the captured traffic.

## Export a PCAP Snapshot

**Kubeshark** enables exporting any query result to merged PCAP files (a PCAP file per node) that can be downloaded as a TAR file using the button with diskette icon that can be found just right to the filter input (section A).

![PCAP Button](/PCAP-button.png)

The PCAP export operation downloads a `tar.gz` file that includes the PCAP file and a file named: `name_resolution_history.json` that helps map dynamically changing IPs to service names.

> **NOTE:** When dealing with a large amount of traffic, this operation can take a few seconds to complete.

## View the PCAP Snapshot

Kubeshark also provides a **CLI** option to view a previously exported PCAP file.

```shell
kubeshark tap --pcap <pcap-snapshot.tar.gz>
```

Running the above command will open Kubeshark in your browser to display the content of the PCAP file.

> **TIP:** You can view the service dependency map of a previously stored PCAP file.




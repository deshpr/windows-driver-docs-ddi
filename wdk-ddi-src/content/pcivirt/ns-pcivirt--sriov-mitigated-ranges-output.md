---
UID: NS.pcivirt._SRIOV_MITIGATED_RANGES_OUTPUT
title: SRIOV_MITIGATED_RANGES_OUTPUT
author: windows-driver-content
description: This structure is the output buffer received by the IOCTL_SRIOV_QUERY_MITIGATED_RANGES request to get the specific ranges on which intercepts must be placed.
old-location: pci\sriov_mitigated_ranges_output.htm
old-project: PCI
ms.assetid: f33f602e-0bce-4ac2-8bd8-8640b2376278
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: SRIOV_MITIGATED_RANGES_OUTPUT, SRIOV_MITIGATED_RANGES_OUTPUT, *PSRIOV_MITIGATED_RANGES_OUTPUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pcivirt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SRIOV_MITIGATED_RANGES_OUTPUT
req.alt-loc: pcivirt.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: 
---

# SRIOV_MITIGATED_RANGES_OUTPUT structure



## -description
<p>This structure is the output buffer received by the <a href="buses.ioctl_sriov_query_mitigated_ranges">IOCTL_SRIOV_QUERY_MITIGATED_RANGES</a> request to get the specific ranges on which intercepts must be placed.</p>


## -syntax

````
typedef struct _SRIOV_MITIGATED_RANGES_OUTPUT {
  ULONG64  BasePageNumber;
  ULONG    PageCount;
  BOOLEAN  InterceptReads;
  BOOLEAN  InterceptWrites;
} SRIOV_MITIGATED_RANGES_OUTPUT, SRIOV_MITIGATED_RANGES_OUTPUT;
````


## -struct-fields
<dl>

### -field BasePageNumber

<dd>
<p>The base address of the allocated region of pages.</p>
</dd>

### -field PageCount

<dd>
<p>Total number of pages.</p>
</dd>

### -field InterceptReads

<dd>
<p>A boolean that indicates the reads intercept bit.</p>
</dd>

### -field InterceptWrites

<dd>
<p>A boolean that indicates the write intercept bit.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Pcivirt.h</dt>
</dl>
</td>
</tr>
</table>
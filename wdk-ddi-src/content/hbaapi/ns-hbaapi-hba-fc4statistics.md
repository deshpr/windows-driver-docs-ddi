---
UID: NS.hbaapi.HBA_FC4Statistics
title: HBA_FC4Statistics
author: windows-driver-content
description: The HBA_FC4Statistics structure contains port statistics.
old-location: storage\hba_fc4statistics.htm
old-project: storage
ms.assetid: e1e37d2c-5688-4528-9cc5-62e70a7561fe
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: HBA_FC4Statistics, HBA_FC4STATISTICS, *PHBA_FC4STATISTICS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbaapi.h
req.include-header: Hbaapi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HBA_FC4STATISTICS
req.alt-loc: hbaapi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.iface: 
---

# HBA_FC4Statistics structure



## -description
<p>The <b>HBA_FC4Statistics</b> structure contains port statistics. </p>


## -syntax

````
typedef struct HBA_FC4Statistics {
  HBA_INT64 InputRequests;
  HBA_INT64 OutputRequests;
  HBA_INT64 ControlRequests;
  HBA_INT64 InputMegabytes;
  HBA_INT64 OutputMegabytes;
} HBA_FC4STATISTICS, *PHBA_FC4STATISTICS;
````


## -struct-fields
<dl>

### -field InputRequests

<dd>
<p>Contains the number of input requests that a port has received.</p>
</dd>

### -field OutputRequests

<dd>
<p>Contains the number of output requests that a port has received.</p>
</dd>

### -field ControlRequests

<dd>
<p>Contains the number of control requests that a port has received.</p>
</dd>

### -field InputMegabytes

<dd>
<p>Contains the number of megabytes of input data that a port has received.</p>
</dd>

### -field OutputMegabytes

<dd>
<p>Contains the number of megabytes of output data that a port has transmitted.</p>
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
<dt>Hbaapi.h (include Hbaapi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\hbaapi\nf-hbaapi-hba-getfc4statistics.md">HBA_GetFC4Statistics</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_FC4Statistics structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
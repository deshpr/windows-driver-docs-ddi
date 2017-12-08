---
UID: NS.d3dkmddi._DXGK_PHYSICALADAPTERCAPS
title: DXGK_PHYSICALADAPTERCAPS
author: windows-driver-content
description: The DXGK_PHYSICALADAPTERCAPS structure is used to report details of a physical adapter.
old-location: display\dxgk_physicaladaptercaps.htm
old-project: display
ms.assetid: 8D075473-605F-4B75-BB02-5B182EEB3B5F
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGK_PHYSICALADAPTERCAPS, DXGK_PHYSICALADAPTERCAPS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_PHYSICALADAPTERCAPS
req.alt-loc: d3dkmddi.h
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

# DXGK_PHYSICALADAPTERCAPS structure



## -description
<p>The <b>DXGK_PHYSICALADAPTERCAPS</b> structure is used to report details of a physical adapter.</p>


## -syntax

````
typedef struct _DXGK_PHYSICALADAPTERCAPS {
  WORD                      NumExecutionNodes;
  WORD                      PagingNodeIndex;
  HANDLE                    DxgkPhysicalAdapterHandle;
  DXGK_PHYSICALADAPTERFLAGS Flags;
  UINT                      VPRPagingNode;
} DXGK_PHYSICALADAPTERCAPS;
````


## -struct-fields
<dl>

### -field NumExecutionNodes

<dd>
<p>The number of execution nodes in the physical adapter.</p>
</dd>

### -field PagingNodeIndex

<dd>
<p>Index of the paging node for the physical adapter.</p>
</dd>

### -field DxgkPhysicalAdapterHandle

<dd>
<p>Handle, which is passed to the kernel mode driver as <b>DXGKRNL_INTERFACE::DeviceHandle</b> in <a href="display.dxgkddistartdevice">DxgkDdiStartDevice</a>. </p>
</dd>

### -field Flags

<dd>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="Flags.IoMmuSupported"></a><a id="flags.iommusupported"></a><a id="FLAGS.IOMMUSUPPORTED"></a><dl>

### -field Flags.IoMmuSupported


### -field TRUE

</dl>
</td>
<td width="60%">
<p>The adapter supports <i>IoMmu</i>.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="Flags.GpuMmuSupported"></a><a id="flags.gpummusupported"></a><a id="FLAGS.GPUMMUSUPPORTED"></a><dl>

### -field Flags.GpuMmuSupported


### -field TRUE

</dl>
</td>
<td width="60%">
<p>The adapter supports <i>GpuMmu</i>.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="Flags.MovePagingSupported"></a><a id="flags.movepagingsupported"></a><a id="FLAGS.MOVEPAGINGSUPPORTED"></a><dl>

### -field Flags.MovePagingSupported


### -field TRUE

</dl>
</td>
<td width="60%">
<p>The adapter supports move paging.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="Flags.VPRPagingContextRequired"></a><a id="flags.vprpagingcontextrequired"></a><a id="FLAGS.VPRPAGINGCONTEXTREQUIRED"></a><dl>

### -field Flags.VPRPagingContextRequired


### -field TRUE

</dl>
</td>
<td width="60%">
<p>The adapter requires the index of the VPR paging node.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -field VPRPagingNode

<dd>
<p>Index of the node to be used for move paging in  the VPR.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 10</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2016</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>
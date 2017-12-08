---
UID: NS.d3d12umddi.D3D12DDI_RESOURCE_UAV_BARRIER
title: D3D12DDI_RESOURCE_UAV_BARRIER
author: windows-driver-content
description: Contains an unordered access view (UAV) barrier.
old-location: display\d3d12ddi_resource_uav_barrier.htm
old-project: display
ms.assetid: 8473EB26-54C5-49D0-A854-422086CE8CCC
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3D12DDI_RESOURCE_UAV_BARRIER, D3D12DDI_RESOURCE_UAV_BARRIER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D12DDI_RESOURCE_UAV_BARRIER
req.alt-loc: D3d12umddi.h
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

# D3D12DDI_RESOURCE_UAV_BARRIER structure



## -description
<p>Contains an unordered access view (UAV) barrier.</p>


## -syntax

````
typedef struct D3D12DDI_RESOURCE_UAV_BARRIER {
  D3D12DDI_HRESOURCE hResource;
} D3D12DDI_RESOURCE_UAV_BARRIER;
````


## -struct-fields
<dl>

### -field hResource

<dd>
<p>The handle of resource.</p>
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
<dt>D3d12umddi.h (include D3d12umddi.h)</dt>
</dl>
</td>
</tr>
</table>
---
UID: NC.d3dkmddi.DXGKDDISETPOWERPSTATE
title: DXGKDDISETPOWERPSTATE
author: windows-driver-content
description: Reserved for system use. Do not use it in your driver.
old-location: display\dxgkddisetpowerpstate.htm
old-project: display
ms.assetid: 58DB4615-BD52-4003-8D60-0881E87C7BD3
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkDdiSetPowerPState
req.alt-loc: D3dkmddi.h
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
---

# DXGKDDISETPOWERPSTATE callback



## -description
Reserved for system use. Do not use it in your driver.


## -prototype

````
PDXGKDDISETPOWERPSTATE DxgkDdiSetPowerPState;

NTSTATUS APIENTRY DxgkDdiSetPowerPState(
  _In_ const HANDLE DriverContext,
  _In_       UINT   ComponentIndex,
  _In_       UINT   RequestedComponentPState
)
{ ... }
````


## -parameters

### -param DriverContext [in]


### -param ComponentIndex [in]


### -param RequestedComponentPState [in]


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows 8.1
</td>
</tr>
<tr>
<th width="30%">
Minimum supported server
</th>
<td width="70%">
Windows Server 2012 R2
</td>
</tr>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
PASSIVE_LEVEL
</td>
</tr>
</table>
---
UID: NS.D3DKMTHK._D3DKMT_CREATE_OUTPUTDUPL
title: _D3DKMT_CREATE_OUTPUTDUPL
author: windows-driver-content
description: Reserved for system use. Do not use in your driver.
old-location: display\d3dkmt_create_outputdupl.htm
old-project: display
ms.assetid: 3fdbf129-331d-4dd5-a417-79c88b7e7947
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _D3DKMT_CREATE_OUTPUTDUPL, D3DKMT_CREATE_OUTPUTDUPL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_CREATE_OUTPUTDUPL
req.alt-loc: D3dkmthk.h
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
---

# _D3DKMT_CREATE_OUTPUTDUPL structure



## -description
Reserved for system use. Do not use in your driver.


## -syntax

````
typedef struct _D3DKMT_CREATE_OUTPUTDUPL {
  D3DKMT_HANDLE                  hAdapter;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
  D3DKMT_HANDLE                  hSharedSurfaceGlobal;
  D3DKMT_HANDLE                  hGPUFencefaceGlobal;
  D3DKMT_HANDLE                  hKeyedMutexGlobal;
} D3DKMT_CREATE_OUTPUTDUPL;
````


## -struct-fields

### -field hAdapter


### -field VidPnSourceId


### -field hSharedSurfaceGlobal


### -field hGPUFencefaceGlobal


### -field hKeyedMutexGlobal


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows 8
</td>
</tr>
<tr>
<th width="30%">
Minimum supported server
</th>
<td width="70%">
Windows Server 2012
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
</table>
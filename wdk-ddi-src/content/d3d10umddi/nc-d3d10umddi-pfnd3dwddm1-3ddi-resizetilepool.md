---
UID: NC.d3d10umddi.PFND3DWDDM1_3DDI_RESIZETILEPOOL
title: PFND3DWDDM1_3DDI_RESIZETILEPOOL
author: windows-driver-content
description: Resizes a tile pool.
old-location: display\resizetilepool.htm
old-project: display
ms.assetid: 184EF418-1B1E-4A10-8F10-1331DF99DCBD
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: SETRESULT_INFO, SETRESULT_INFO, *PSETRESULT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1,WDDM 1.3
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ResizeTilePool
req.alt-loc: D3d10umddi.h
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

# PFND3DWDDM1_3DDI_RESIZETILEPOOL callback



## -description
<p>Resizes a tile pool.

</p>


## -prototype

````
PFND3DWDDM1_3DDI_RESIZETILEPOOL ResizeTilePool;

VOID APIENTRY* ResizeTilePool(
   D3D10DDI_HDEVICE   hDevice,
   D3D10DDI_HRESOURCE hTilePool,
   UINT64             NewSizeInBytes
)
{ ... }
````


## -parameters
<dl>

### -param hDevice 

<dd>
<p>A handle to the display device (graphics context).</p>
</dd>

### -param hTilePool 

<dd>
<p>A handle to the tile pool to resize.</p>
</dd>

### -param NewSizeInBytes 

<dd>
<p>The new size, in bytes, of the tile pool. The size must be a multiple of 64 KB or zero.</p>
</dd>
</dl>

## -returns
<p>None</p>

<p>The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-seterror-cb.md">pfnSetErrorCb</a> callback function to set an error code. Returns <b>S_OK</b> if successful; otherwise, returns one of the following:</p><dl>
<dt><b>E_INVALIDARG</b></dt>
</dl><p>The new tile pool size isn't a multiple of 64 KB or zero. The existing tile pool remains unchanged, which includes existing mappings.</p><dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl><p>The driver had to allocate space for new page table mappings but ran out of memory. The existing tile pool remains unchanged, which includes existing mappings.</p>

<p> </p>

<p>The Direct3D runtime performs minimal validation of parameters, but it will fail the call if the new tile pool size isn't a multiple of the tile size, or zero.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8.1</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012 R2</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>WDDM 1.3</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>
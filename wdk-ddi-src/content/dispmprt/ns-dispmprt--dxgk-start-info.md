---
UID: NS.dispmprt._DXGK_START_INFO
title: DXGK_START_INFO
author: windows-driver-content
description: The DXGK_START_INFO structure holds information that is needed by the display miniport driver's DxgkDdiStartDevice function.
old-location: display\dxgk_start_info.htm
old-project: display
ms.assetid: 4d28bc79-5145-48a0-99e8-3f81b2ec4a05
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGK_START_INFO, DXGK_START_INFO, *PDXGK_START_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_START_INFO
req.alt-loc: dispmprt.h
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

# DXGK_START_INFO structure



## -description
<p>The DXGK_START_INFO structure holds information that is needed by the display miniport driver's <a href="display.dxgkddistartdevice">DxgkDdiStartDevice</a> function.</p>


## -syntax

````
typedef struct _DXGK_START_INFO {
  ULONG RequiredDmaQueueEntry;
  GUID  AdapterGuid;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN8)
  LUID  AdapterLuid;
#endif 
} DXGK_START_INFO, *PDXGK_START_INFO;
````


## -struct-fields
<dl>

### -field RequiredDmaQueueEntry

<dd>
<p>The number of DMA buffers that the display miniport driver (or the display adapter) must be able to hold in a queue. The display miniport driver must preallocate all resources required to accommodate this number of DMA buffers. </p>
</dd>

### -field AdapterGuid

<dd>
<p>A GUID that will serve as an identifier for the adapter being started.</p>
</dd>

### -field AdapterLuid

<dd>
<p>Available starting with Windows 8.</p>
<p>A locally unique identifier (LUID) that will serve as an identifier for the adapter being started.</p>
</dd>
</dl>

## -remarks
<p>The DirectX graphics kernel subsystem submits DMA buffers to the display miniport driver by calling <a href="display.dxgkddisubmitcommand">DxgkDdiSubmitCommand</a>.</p>

<p>The <i>DxgkStartInfo</i> parameter of the <a href="display.dxgkddistartdevice">DxgkDdiStartDevice</a> function is a pointer to a DXGK_START_INFO structure. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Dispmprt.h (include Dispmprt.h)</dt>
</dl>
</td>
</tr>
</table>
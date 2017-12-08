---
UID: NF.wdfhwaccess.WDF_WRITE_PORT_BUFFER_USHORT
title: WDF_WRITE_PORT_BUFFER_USHORT
author: windows-driver-content
description: The WDF_WRITE_PORT_BUFFER_USHORT function writes a number of USHORT values from a buffer to the specified port address.
old-location: wdf\wdf_write_port_buffer_ushort.htm
old-project: wdf
ms.assetid: 7E4638B0-6FFE-483A-8B71-33B939854CFA
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WDF_WRITE_PORT_BUFFER_USHORT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfhwaccess.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.0
req.alt-api: WDF_WRITE_PORT_BUFFER_USHORT
req.alt-loc: Wdfhwaccess.h
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
req.product: Windows 10 or later.
---

# WDF_WRITE_PORT_BUFFER_USHORT function



## -description
<p class="CCE_Message">[Applies to UMDF only]</p>
<p>The <b>WDF_WRITE_PORT_BUFFER_USHORT</b> function writes a number of USHORT values from a buffer to the specified port address. 
</p>


## -syntax

````
void WDF_WRITE_PORT_BUFFER_USHORT(
  _In_ WDFDEVICE Device,
  _In_ PUSHORT   Port,
  _In_ PUSHORT   Buffer,
  _In_ ULONG     Count 
);
````


## -parameters
<dl>

### -param Device [in]

<dd>
<p>A handle to a framework device object.</p>
</dd>

### -param Port [in]

<dd>
<p>A pointer to the port, which must be a mapped memory range in I/O space.
</p>
</dd>

### -param Buffer [in]

<dd>
<p>A pointer to a buffer from which an array of USHORT values is to be written.
</p>
</dd>

### -param Count  [in]

<dd>
<p>Specifies the number of USHORT values to be written to the buffer.</p>
</dd>
</dl>

## -returns
<p>This function does not return a value.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum support</p>
</th>
<td width="70%">
<p>Windows 8.1</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>2.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdfhwaccess.h</dt>
</dl>
</td>
</tr>
</table>
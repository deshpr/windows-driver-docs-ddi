---
UID: NF.wdm.READ_REGISTER_BUFFER_ULONG~r1
title: READ_REGISTER_BUFFER_ULONG
author: windows-driver-content
description: The READ_REGISTER_BUFFER_ULONG routine reads a number of ULONG values from the specified register address into a buffer.
old-location: kernel\read_register_buffer_ulong.htm
old-project: kernel
ms.assetid: a80d361e-81d3-483c-8ddb-d5e5a69c8ba4
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: READ_REGISTER_BUFFER_ULONG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: READ_REGISTER_BUFFER_ULONG
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level (see Remarks section)
req.iface: 
req.product: Windows 10 or later.
---

# READ_REGISTER_BUFFER_ULONG function



## -description
<p>The <b>READ_REGISTER_BUFFER_ULONG</b> routine reads a number of ULONG values from the specified register address into a buffer. </p>


## -syntax

````
VOID READ_REGISTER_BUFFER_ULONG(
  _In_  PULONG Register,
  _Out_ PULONG Buffer,
  _In_  ULONG  Count
);
````


## -parameters
<dl>

### -param Register [in]

<dd>
<p>Pointer to the register, which must be a mapped range in memory space.</p>
</dd>

### -param Buffer [out]

<dd>
<p>Pointer to a buffer into which an array of ULONG values is read.</p>
</dd>

### -param Count [in]

<dd>
<p>Specifies the number of ULONG values to be read into the buffer. </p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>The size of the buffer must be large enough to contain at least the specified number of ULONG values.</p>

<p>Callers of <b>READ_REGISTER_BUFFER_ULONG</b> can be running at any IRQL, assuming the <i>Buffer</i> is resident and the <i>Register</i> is resident, mapped device memory.</p>

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
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows 2000.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>Any level (see Remarks section)</p>
</td>
</tr>
</table>
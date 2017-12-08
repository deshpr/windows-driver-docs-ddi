---
UID: NF.dbgeng.IDebugDataSpaces3.ReadPhysical
title: IDebugDataSpaces3::ReadPhysical
author: windows-driver-content
description: The ReadPhysical method reads the target's memory from the specified physical address.
old-location: debugger\readphysical3.htm
old-project: debugger
ms.assetid: 8df51985-9208-46ce-8802-6bc5ec707ab2
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugDataSpaces3, ReadPhysical, IDebugDataSpaces3::ReadPhysical
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugDataSpaces.ReadPhysical,IDebugDataSpaces2.ReadPhysical,IDebugDataSpaces3.ReadPhysical,IDebugDataSpaces4.ReadPhysical
req.alt-loc: dbgeng.h
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
req.iface: IDebugDataSpaces3
---

# IDebugDataSpaces3::ReadPhysical method



## -description
<p>The <b>ReadPhysical</b> method reads the target's memory from the specified physical address.</p>


## -syntax

````
HRESULT ReadPhysical(
  [in]            ULONG64 Offset,
  [out]           PVOID   Buffer,
  [in]            ULONG   BufferSize,
  [out, optional] PULONG  BytesRead
);
````


## -parameters
<dl>

### -param Offset [in]

<dd>
<p>Specifies the physical address of the memory to read.</p>
</dd>

### -param Buffer [out]

<dd>
<p>Receives the memory that is read.</p>
</dd>

### -param BufferSize [in]

<dd>
<p>Specifies the size in bytes of the buffer <i>Buffer</i>.  This is the maximum number of bytes that will be read.</p>
</dd>

### -param BytesRead [out, optional]

<dd>
<p>Receives the number of bytes read from the target's memory.  If <i>BytesRead</i> is <b>NULL</b>, this information is not returned.</p>
</dd>
</dl>

## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p>

<p> </p>

<p>This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.</p>

## -remarks
<p>This method is only available in kernel-mode debugging.</p>

## -requirements
<table>
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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Dbgeng.h (include Dbgeng.h)</dt>
</dl>
</td>
</tr>
</table>
---
UID: NF.ntifs.FsRtlRemoveDotsFromPath
title: FsRtlRemoveDotsFromPath function
author: windows-driver-content
description: The FsRtlRemoveDotsFromPath routine removes unnecessary occurrences of '.' and '..' from the specified path.
old-location: ifsk\fsrtlremovedotsfrompath.htm
old-project: ifsk
ms.assetid: af6ecdb7-8713-460d-8fd9-ef027ac15b39
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FsRtlRemoveDotsFromPath
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FsRtlRemoveDotsFromPath
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
req.irql: PASSIVE_LEVEL
---

# FsRtlRemoveDotsFromPath function



## -description
The <b>FsRtlRemoveDotsFromPath</b> routine removes unnecessary occurrences of '.' and '..' from the specified path.


## -syntax

````
NTSTATUS FsRtlRemoveDotsFromPath(
  _Inout_ PWSTR  OriginalString,
  _In_    USHORT PathLength,
  _Out_   USHORT *NewLength
);
````


## -parameters

### -param OriginalString [in, out]

A pointer to the buffer to be processed.

### -param PathLength [in]

The length of buffer (in bytes).

### -param NewLength [out]

A pointer to the new length of the buffer, after processing.

## -returns
The<b> FsRtlRemoveDotsFromPath</b> routine returns either STATUS_SUCCESS value for success or STATUS_IO_REPARSE_DATA_INVALID if the operation could not be completed.

## -remarks
This routine would take a path as <i>OriginalString</i> like the following example:

The routine would modify <i>OriginalString</i> as follows:

The routine will fail with STATUS_IO_REPARSE_DATA_INVALID if any of the following strings are passed as <i>OriginalString</i>:

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
 Available in Windows Vista and later versions of the Windows operating system.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include FltKernel.h or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
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
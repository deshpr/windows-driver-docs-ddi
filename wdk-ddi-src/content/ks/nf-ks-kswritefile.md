---
UID: NF.ks.KsWriteFile
title: KsWriteFile function
author: windows-driver-content
description: The KsWriteFile function performs a write against the specified file object.
old-location: stream\kswritefile.htm
old-project: stream
ms.assetid: ed66db40-d159-4660-96c0-da52f752a409
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KsWriteFile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsWriteFile
req.alt-loc: Ks.lib,Ks.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: 
---

# KsWriteFile function



## -description
The <b>KsWriteFile</b> function performs a write against the specified file object. It is assumed that the caller is serializing access to the file for operations against a FO_SYNCHRONOUS_IO file object. The function attempts to use <b>FastIoDispatch</b> if possible, or it generates a write request against the device object. All relevant statistics are updated.


## -syntax

````
NTSTATUS KsWriteFile(
  _In_     PFILE_OBJECT     FileObject,
  _In_opt_ PKEVENT          Event,
  _In_opt_ PVOID            PortContext,
  _Out_    PIO_STATUS_BLOCK IoStatusBlock,
  _In_     PVOID            Buffer,
  _In_     ULONG            Length,
  _In_opt_ ULONG            Key,
  _In_     KPROCESSOR_MODE  RequestorMode
);
````


## -parameters

### -param FileObject [in]

Specifies the file object to perform the read against.

### -param Event [in, optional]

Optionally contains the event to use in the write. If no event is passed, the call is assumed to be on a synchronous file object or the caller is waiting for the file object's event. If the call is not on a synchronous file object, it can be asynchronously completed. If the file has been opened for synchronous I/O, this variable must be <b>NULL</b>. If this variable is used, it must be an event allocated by the object manager.

### -param PortContext [in, optional]

Optionally contains context information for a completion port.

### -param IoStatusBlock [out]

Indicates the location in which to return the status information. This is always assumed to be a valid address, regardless of the requester mode.

### -param Buffer [in]

Specifies the buffer from which to write the data. If the buffer needs to be probed and locked, an exception handler is used, along with <i>RequesterMode</i>.

### -param Length [in]

Specifies the size of the buffer passed.

### -param Key [in, optional]

Optionally contains a key, or zero if none.

### -param RequestorMode [in]

Indicates the processor mode to place in the read IRP if one needs to be generated. Additionally, it is used if a buffer needs to be probed and locked. This variable also determines if a fast I/O call can be performed. If the requester mode is not KernelMode, but the previous mode was, then fast I/O cannot be used.

## -returns
The <b>KsWriteFile</b> function returns STATUS_SUCCESS if successful, STATUS_PENDING if action is pending, or it returns a read error if unsuccessful.

## -remarks


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
Header
</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Ks.lib</dt>
</dl>
</td>
</tr>
</table>
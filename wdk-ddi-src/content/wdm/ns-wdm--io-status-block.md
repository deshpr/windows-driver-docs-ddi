---
UID: NS.wdm._IO_STATUS_BLOCK
title: IO_STATUS_BLOCK
author: windows-driver-content
description: A driver sets an IRP's I/O status block to indicate the final status of an I/O request, before calling IoCompleteRequest for the IRP.
old-location: kernel\io_status_block.htm
old-project: kernel
ms.assetid: 1ce2b1d0-a8b2-4a05-8895-e13802690a7b
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: IO_STATUS_BLOCK, IO_STATUS_BLOCK, *PIO_STATUS_BLOCK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IO_STATUS_BLOCK
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.iface: 
req.product: Windows 10 or later.
---

# IO_STATUS_BLOCK structure



## -description
<p>A driver sets an IRP's I/O status block to indicate the final status of an I/O request, before calling <a href="..\wdm\nf-wdm-iocompleterequest.md">IoCompleteRequest</a> for the IRP.</p>


## -syntax

````
typedef struct _IO_STATUS_BLOCK {
  union {
    NTSTATUS Status;
    PVOID    Pointer;
  };
  ULONG_PTR Information;
} IO_STATUS_BLOCK, *PIO_STATUS_BLOCK;
````


## -struct-fields
<dl>

### -field Status

<dd>
<p>This is the completion status, either STATUS_SUCCESS if the requested operation was completed successfully or an informational, warning, or error STATUS_<i>XXX</i> value. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565436">Using NTSTATUS values</a>.</p>
</dd>

### -field Pointer

<dd>
<p>Reserved. For internal use only.</p>
</dd>

### -field Information

<dd>
<p>This is set to a request-dependent value. For example, on successful completion of a transfer request, this is set to the number of bytes transferred. If a transfer request is completed with another STATUS_<i>XXX</i>, this member is set to zero. </p>
</dd>
</dl>

## -remarks
<p>Unless a driver's dispatch routine completes an IRP with an error status value, the lowest-level driver in the chain frequently sets the IRP's I/O status block to the values that will be returned to the original requester of the I/O operation.</p>

<p>The <a href="..\wdm\nc-wdm-io-completion-routine.md">IoCompletion</a> routines of higher-level drivers usually check the I/O status block in IRPs completed by lower drivers. By design, the I/O status block in an IRP is the only information passed back from the underlying device driver to all higher-level drivers' <i>IoCompletion</i> routines.</p>

<p>The operating system implements <a href="kernel.driver_support_routines">support routines</a> that write <b>IO_STATUS_BLOCK</b> values to caller-supplied output buffers. For example, see <a href="..\wdm\nf-wdm-zwopenfile.md">ZwOpenFile</a> or <a href="http://go.microsoft.com/fwlink/p/?linkid=155044">NtOpenFile</a>. These routines return status codes that might not match the status codes in the <b>IO_STATUS_BLOCK</b> structures. If one of these routines returns STATUS_PENDING, the caller should wait for the I/O operation to complete, and then check the status code in the <b>IO_STATUS_BLOCK</b> structure to determine the final status of the operation. If the routine returns a status code other than STATUS_PENDING, the caller should rely on this status code instead of the status code in the <b>IO_STATUS_BLOCK</b> structure.</p>

<p>For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff551825">I/O Status Blocks</a>.</p>

## -requirements
<table>
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
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\ns-wdm--io-stack-location.md">IO_STACK_LOCATION</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iocompleterequest.md">IoCompleteRequest</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iosetcompletionroutine.md">IoSetCompletionRoutine</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm--irp.md">IRP</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IO_STATUS_BLOCK structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
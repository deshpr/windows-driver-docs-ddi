---
UID: NC.parallel.PPARALLEL_WRITE
title: PPARALLEL_WRITE
author: windows-driver-content
description: The PPARALLEL_WRITE-typed callback routine writes data to a parallel device. The system-supplied bus driver for parallel ports supplies this routine.
old-location: parports\pparallel_write.htm
old-project: parports
ms.assetid: 4973b1e2-5828-40d1-bb2e-da67a406eafa
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RegisterOpRegionHandler
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: parallel.h
req.include-header: Parallel.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PPARALLEL_WRITE
req.alt-loc: parallel.h
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

# PPARALLEL_WRITE callback



## -description
<p>The PPARALLEL_WRITE-typed callback routine writes data to a parallel device. The system-supplied bus driver for parallel ports supplies this routine.</p>


## -prototype

````
typedef NTSTATUS ( *PPARALLEL_WRITE)(
  _In_  PVOID  Context,
  _In_  PVOID  Buffer,
  _In_  ULONG  NumBytesToWrite,
  _Out_ PULONG NumBytesWritten,
  _In_  UCHAR  Channel
);
````


## -parameters
<dl>

### -param Context [in]

<dd>
<p>Pointer to the device extension of a parallel device's physical device object (<a href="wdkgloss.p#wdkgloss.pdo#wdkgloss.pdo"><i>PDO</i></a>).</p>
</dd>

### -param Buffer [in]

<dd>
<p>Pointer to a caller-allocated write buffer.</p>
</dd>

### -param NumBytesToWrite [in]

<dd>
<p>Specifies the number of bytes to copy from the write buffer to the parallel device. Must be less than or equal to the number of bytes in the caller-allocated write buffer.</p>
</dd>

### -param NumBytesWritten [out]

<dd>
<p>Specifies the number of bytes that were actually copied from the caller-allocated write buffer to the parallel device.</p>
</dd>

### -param Channel [in]

<dd>
<p>Not used.</p>
</dd>
</dl>

## -returns
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><p>The caller-supplied data was successfully transferred to the device.</p><dl>
<dt><b>STATUS_<i>Xxx</i></b></dt>
</dl><p>An internal operation resulted in an NTSTATUS error.</p>

<p> </p>

## -remarks
<p>To obtain a pointer to the system-supplied PPARALLEL_WRITE callback, a kernel-mode driver uses an <a href="..\parallel\ni-parallel-ioctl-internal-parclass-connect.md">IOCTL_INTERNAL_PARCLASS_CONNECT</a> request, which returns a <a href="..\parallel\ns-parallel--parclass-information.md">PARCLASS_INFORMATION</a> structure. The <b>ParallelWrite</b> member of the PARCLASS_INFORMATION structure is a pointer to this callback.</p>

<p>A client can only use this routine if it has a lock on a parallel port. A client obtains a lock on a parallel port by using an <a href="..\parallel\ni-parallel-ioctl-internal-lock-port.md">IOCTL_INTERNAL_LOCK_PORT</a> request.</p>

<p>The PPARALLEL_WRITE callback runs in the caller's thread at the IRQL of the caller.</p>

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
<dt>Parallel.h (include Parallel.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\parallel\ni-parallel-ioctl-internal-lock-port.md">IOCTL_INTERNAL_LOCK_PORT</a>
</dt>
<dt>
<a href="..\parallel\nc-parallel-pparallel-read.md">PPARALLEL_READ</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20PPARALLEL_WRITE function pointer%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
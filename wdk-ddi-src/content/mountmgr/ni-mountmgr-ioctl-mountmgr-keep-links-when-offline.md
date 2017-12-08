---
UID: NI.mountmgr.IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE
title: IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE
author: windows-driver-content
description: This IOCTL directs the mount manager to keep a symbolic link active after the Plug and Play manager has given notification that its corresponding volume has gone offline.
old-location: storage\ioctl_mountmgr_keep_links_when_offline.htm
old-project: storage
ms.assetid: 56af77f9-7c29-4bde-a8ae-9af23af4d296
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: MOUNTDEV_UNIQUE_ID, MOUNTDEV_UNIQUE_ID, *PMOUNTDEV_UNIQUE_ID
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: mountmgr.h
req.include-header: Mountmgr.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE
req.alt-loc: Mountmgr.h
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

# IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE IOCTL



## -description
<p>This IOCTL directs the mount manager to keep a symbolic link active after the Plug and Play manager has given notification that its corresponding volume has gone offline. When the volume goes back online, the mount manager reassigns the symbolic link to the volume. No other volume is allowed to claim the symbolic link while its original owner is offline.</p>
<p>Clusters use this IOCTL to ensure that a node can continue to access a volume with the same drive letter, even if the volume is not continually present in the system.</p>


## -ioctlparameters

### -input-buffer
<p>The mount manager client loads the following structure with the symbolic link that will persist even after its volume is removed from the system. The initialized structure <a href="..\mountmgr\ns-mountmgr--mountmgr-target-name.md">MOUNTMGR_TARGET_NAME</a>, defined in <i>Mountmgr.h</i>, is inserted at the beginning of the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.</p>

### -input-buffer-length
<p><b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be greater than or equal to <b>sizeof</b>(MOUNTMGR_TARGET_NAME).</p>

<p><b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be greater than or equal to <b>sizeof</b>(MOUNTMGR_TARGET_NAME).</p>

### -output-buffer
<p>None</p>

<p>None</p>

<p>None</p>

### -output-buffer-length
<p>None</p>

<p>None</p>

<p>None</p>

<p>None</p>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<p>If the operation is successful, the <b>Status</b> field is set to STATUS_SUCCESS.</p>

<p>The input buffer size, indicated by <b>InputBufferLength</b>, must be large enough to hold the structure MOUNTMGR_TARGET_NAME and the symbolic link name that follows it. If it is not large enough, the <b>Status</b> field is set to STATUS_INVALID_PARAMETER.</p>

<p>If the operation is successful, the <b>Status</b> field is set to STATUS_SUCCESS.</p>

<p>The input buffer size, indicated by <b>InputBufferLength</b>, must be large enough to hold the structure MOUNTMGR_TARGET_NAME and the symbolic link name that follows it. If it is not large enough, the <b>Status</b> field is set to STATUS_INVALID_PARAMETER.</p>

<p>If the operation is successful, the <b>Status</b> field is set to STATUS_SUCCESS.</p>

<p>The input buffer size, indicated by <b>InputBufferLength</b>, must be large enough to hold the structure MOUNTMGR_TARGET_NAME and the symbolic link name that follows it. If it is not large enough, the <b>Status</b> field is set to STATUS_INVALID_PARAMETER.</p>

<p>If the operation is successful, the <b>Status</b> field is set to STATUS_SUCCESS.</p>

<p>The input buffer size, indicated by <b>InputBufferLength</b>, must be large enough to hold the structure MOUNTMGR_TARGET_NAME and the symbolic link name that follows it. If it is not large enough, the <b>Status</b> field is set to STATUS_INVALID_PARAMETER.</p>

<p>If the operation is successful, the <b>Status</b> field is set to STATUS_SUCCESS.</p>

<p>The input buffer size, indicated by <b>InputBufferLength</b>, must be large enough to hold the structure MOUNTMGR_TARGET_NAME and the symbolic link name that follows it. If it is not large enough, the <b>Status</b> field is set to STATUS_INVALID_PARAMETER.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Mountmgr.h (include Mountmgr.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\mountmgr\ns-mountmgr--mountmgr-target-name.md">MOUNTMGR_TARGET_NAME</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE control code%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
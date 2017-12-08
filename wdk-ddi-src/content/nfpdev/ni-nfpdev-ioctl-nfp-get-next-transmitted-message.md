---
UID: NI.nfpdev.IOCTL_NFP_GET_NEXT_TRANSMITTED_MESSAGE
title: IOCTL_NFP_GET_NEXT_TRANSMITTED_MESSAGE
author: windows-driver-content
description: A client interested in receiving notifications that a message has been transmitted will send the IOCTL_NFP_GET_NEXT_TRANSMITTED_MESSAGE request to the proximity driver.
old-location: nfpdrivers\ioctl_nfp_get_next_transmitted_message.htm
old-project: nfpdrivers
ms.assetid: 3E8B47B5-D774-4D37-BA57-FAB49C9DE9A3
ms.author: windowsdriverdev
ms.date: 11/27/2017
ms.keywords: SECURE_ELEMENT_TECH_ROUTING_INFO, SECURE_ELEMENT_TECH_ROUTING_INFO, *PSECURE_ELEMENT_TECH_ROUTING_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: nfpdev.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_NFP_GET_NEXT_TRANSMITTED_MESSAGE
req.alt-loc: nfpdev.h
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

# IOCTL_NFP_GET_NEXT_TRANSMITTED_MESSAGE IOCTL



## -description
<p>A client interested in receiving notifications that a message has been transmitted will send the <b>IOCTL_NFP_GET_NEXT_TRANSMITTED_MESSAGE</b> request to the proximity driver.</p>


## -ioctlparameters

### -input-buffer
<p>None</p>

### -input-buffer-length

<text></text>

### -output-buffer
<p>None</p>

<p>None</p>

### -output-buffer-length

<text></text>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.
Otherwise, Status to the appropriate error condition as a NTSTATUS code. 
For more information, see [XREF-LINK:NTSTATUS Values].

## -remarks
<p> A client application will send this IOCTL in a control loop to the publication handle.  Two separate transmissions of the same message would result in triggering two events.</p>

<p>The client should send another IOCTL each time the pended one is completed.  The driver MUST use appropriate locks to guarantee that the number of successful completions of this IOCTL equates to the number of times the publication has been transmitted.</p>

<p>The following actions are required when using this IOCTL:<ul>
<li>
<p>If this IOCTL is received on a handle that hasn’t previously succeeded an <a href="..\nfpdev\ni-nfpdev-ioctl-nfp-set-payload.md">IOCTL_NFP_SET_PAYLOAD</a>, the driver MUST complete it with STATUS_INVALID_DEVICE_STATE.</p>
</li>
<li>
<p>The driver must maintain the equivalent of a “CompleteEventImmediately” counter (<b>ULONG</b> or larger) in the publication file handle.</p>
</li>
<li>
<p>	When this IOCTL is received in the driver:</p>
<ul>
<li>
<p>If the counter is zero, then the driver MUST pend the IOCTL for later completion.</p>
</li>
<li>
<p>	If the counter is greater than zero, then the driver MUST decrement the counter by one and complete the IOCTL with STATUS_SUCCESS immediately.</p>
</li>
</ul>
</li>
<li>
<p>If the publication is transmitted and no IOCTL is currently pended, the driver MUST increment the “CompleteEventImmediately” counter by one.</p>
</li>
<li>
<p>	If the publication is transmitted while there is a pended IOCTL available, the driver MUST complete the pended IRP with STATUS_SUCCESS and NOT increment the “CompleteEventImmediately” counter.</p>
</li>
<li>
<p>	If the IOCTL contains an input or output buffer the driver MUST complete the IOCTL with STATUS_INVALID_PARAMETER.</p>
</li>
<li>
<p>	If this IOCTL is received while another is currently pended in the publication handle, the second one (or later) MUST be completed with STATUS_INVALID_DEVICE_STATE.</p>
</li>
<li>
<p>The driver MUST support CancelIo of the pended IOCTL.</p>
</li>
</ul>
</p>

<p>If this IOCTL is received on a handle that hasn’t previously succeeded an <a href="..\nfpdev\ni-nfpdev-ioctl-nfp-set-payload.md">IOCTL_NFP_SET_PAYLOAD</a>, the driver MUST complete it with STATUS_INVALID_DEVICE_STATE.</p>

<p>The driver must maintain the equivalent of a “CompleteEventImmediately” counter (<b>ULONG</b> or larger) in the publication file handle.</p>

<p>	When this IOCTL is received in the driver:</p>

<p>If the counter is zero, then the driver MUST pend the IOCTL for later completion.</p>

<p>	If the counter is greater than zero, then the driver MUST decrement the counter by one and complete the IOCTL with STATUS_SUCCESS immediately.</p>

<p>If the publication is transmitted and no IOCTL is currently pended, the driver MUST increment the “CompleteEventImmediately” counter by one.</p>

<p>	If the publication is transmitted while there is a pended IOCTL available, the driver MUST complete the pended IRP with STATUS_SUCCESS and NOT increment the “CompleteEventImmediately” counter.</p>

<p>	If the IOCTL contains an input or output buffer the driver MUST complete the IOCTL with STATUS_INVALID_PARAMETER.</p>

<p>	If this IOCTL is received while another is currently pended in the publication handle, the second one (or later) MUST be completed with STATUS_INVALID_DEVICE_STATE.</p>

<p>The driver MUST support CancelIo of the pended IOCTL.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Windows 8</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Nfpdev.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) overall design guide</a></dt>
<dt><a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfp-design-guide">Near field proximity design guide (Tap and Do, NFP provider model, driver requirements)</a></dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20IOCTL_NFP_GET_NEXT_TRANSMITTED_MESSAGE control code%20 RELEASE:%20(11/27/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
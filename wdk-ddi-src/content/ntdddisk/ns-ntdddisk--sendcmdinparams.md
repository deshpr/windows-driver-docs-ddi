---
UID: NS.ntdddisk._SENDCMDINPARAMS
title: SENDCMDINPARAMS
author: windows-driver-content
description: The SENDCMDINPARAMS structure contains the input parameters for the SMART_SEND_DRIVE_COMMAND request.
old-location: storage\sendcmdinparams.htm
old-project: storage
ms.assetid: 4c02da7e-2d93-4e0c-9666-acb380c6d39a
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: SENDCMDINPARAMS, SENDCMDINPARAMS, *PSENDCMDINPARAMS, *LPSENDCMDINPARAMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SENDCMDINPARAMS
req.alt-loc: ntdddisk.h
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

# SENDCMDINPARAMS structure



## -description
<p>The SENDCMDINPARAMS structure contains the input parameters for the <a href="storage.smart_send_drive_command">SMART_SEND_DRIVE_COMMAND</a> request.</p>


## -syntax

````
typedef struct _SENDCMDINPARAMS {
  ULONG   cBufferSize;
  IDEREGS irDriveRegs;
  UCHAR   bDriveNumber;
  UCHAR   bReserved[3];
  ULONG   dwReserved[4];
  UCHAR   bBuffer[1];
} SENDCMDINPARAMS, *PSENDCMDINPARAMS, *LPSENDCMDINPARAMS;
````


## -struct-fields
<dl>

### -field cBufferSize

<dd>
<p>Contains the buffer size, in bytes.</p>
</dd>

### -field irDriveRegs

<dd>
<p>Contains a <a href="..\ntdddisk\ns-ntdddisk--ideregs.md">IDEREGS</a> structure used to report the contents of the IDE controller registers.</p>
</dd>

### -field bDriveNumber

<dd>
<p>The <b>bDriveNumber</b> member is opaque. Do not use it. The operating system ignores this member, because the physical drive that receives the request depends on the handle that the caller uses when making the request.</p>
</dd>

### -field bReserved

<dd>
<p>Reserved. </p>
</dd>

### -field dwReserved

<dd>
<p>Reserved. </p>
</dd>

### -field bBuffer

<dd>
<p>Pointer to the input buffer. </p>
</dd>
</dl>

## -remarks
<p>The <a href="storage.smart_send_drive_command">SMART_SEND_DRIVE_COMMAND</a> is used to send a Self-Monitoring Analysis and Reporting Technology (SMART) commands to a device. </p>

<p>The SENDCMDINPARAMS structure is also used with the <a href="storage.smart_rcv_drive_data">SMART_RCV_DRIVE_DATA</a> request. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntdddisk.h (include Ntdddisk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.smart_send_drive_command">SMART_SEND_DRIVE_COMMAND</a>
</dt>
<dt>
<a href="storage.smart_rcv_drive_data">SMART_RCV_DRIVE_DATA</a>
</dt>
<dt>
<a href="..\ntdddisk\ns-ntdddisk--sendcmdoutparams.md">SENDCMDOUTPARAMS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SENDCMDINPARAMS structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
---
UID: NS.usb._URB_CONTROL_GET_INTERFACE_REQUEST
title: URB_CONTROL_GET_INTERFACE_REQUEST
author: windows-driver-content
description: The _URB_CONTROL_GET_INTERFACE_REQUEST structure is used by USB client drivers to retrieve the current alternate interface setting for an interface in the current configuration.
old-location: buses\_urb_control_get_interface_request.htm
old-project: usbref
ms.assetid: 64f843ba-8462-48d4-ba3a-a028bb921880
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: URB_CONTROL_GET_INTERFACE_REQUEST,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usb.h
req.include-header: Usb.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: _URB_CONTROL_GET_INTERFACE_REQUEST
req.alt-loc: usb.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# URB_CONTROL_GET_INTERFACE_REQUEST structure



## -description
<p>The <b>_URB_CONTROL_GET_INTERFACE_REQUEST</b> structure is used by USB client drivers to retrieve the current alternate interface setting for an interface in the current configuration.</p>


## -syntax

````
struct _URB_CONTROL_GET_INTERFACE_REQUEST {
  struct URB_HEADER  Hdr;
  PVOID               Reserved;
  ULONG               Reserved0;
  ULONG               TransferBufferLength;
  PVOID               TransferBuffer;
  PMDL                TransferBufferMDL;
  struct URB  *UrbLink;
  struct URB_HCD_AREA  hca;
  UCHAR               Reserved1[4];
  USHORT              Interface;
  USHORT              Reserved2;
};
````


## -struct-fields
<dl>

### -field Hdr

<dd>
<p>Pointer to a <a href="buses._urb_header">_URB_HEADER</a> structure that specifies the URB header information. <b>Hdr.Function</b> must be URB_FUNCTION_GET_INTERFACE, and <b>Hdr.Length</b> must equal <code>sizeof(_URB_CONTROL_GET_INTERFACE_REQUEST)</code>.</p>
</dd>

### -field Reserved

<dd>
<p>Reserved. Do not use.</p>
</dd>

### -field Reserved0

<dd>
<p>Reserved. Do not use.</p>
</dd>

### -field TransferBufferLength

<dd>
<p>Must be 1. This member specifies the length, in bytes, of the buffer specified in <b>TransferBuffer</b> or described in <b>TransferBufferMDL</b>. The host controller driver returns the number of bytes sent to or read from the pipe in this member.</p>
</dd>

### -field TransferBuffer

<dd>
<p>Pointer to a resident buffer for the transfer or is <b>NULL</b> if an MDL is supplied in <b>TransferBufferMDL</b>. The bus driver returns a single byte specifying the index of the current alternate setting for the interface.</p>
</dd>

### -field TransferBufferMDL

<dd>
<p>Pointer to an MDL that describes a resident buffer or is <b>NULL</b> if a buffer is supplied in <b>TransferBuffer</b>. The bus driver returns a single byte specifying the index of the current alternate setting for the interface. This MDL must be allocated from nonpaged pool.</p>
</dd>

### -field UrbLink

<dd>
<p>Reserved. Do not use.</p>
</dd>

### -field hca

<dd>
<p>Reserved. Do not use.</p>
</dd>

### -field Reserved1

<dd>
<p>Reserved. Do not use.</p>
</dd>

### -field Interface

<dd>
<p>Specifies the device-defined index of the interface descriptor being retrieved.</p>
</dd>

### -field Reserved2

<dd>
<p>Reserved. Do not use.</p>
</dd>
</dl>

## -remarks
<p>The reserved members of this structure must be treated as opaque and are reserved for system use.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Usb.h (include Usb.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\usb\ns-usb--urb.md">URB</a>
</dt>
<dt>
<a href="buses._urb_header">_URB_HEADER</a>
</dt>
<dt>
<a href="buses.usb_structures_and_enumerations">USB Structures</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20_URB_CONTROL_GET_INTERFACE_REQUEST structure%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
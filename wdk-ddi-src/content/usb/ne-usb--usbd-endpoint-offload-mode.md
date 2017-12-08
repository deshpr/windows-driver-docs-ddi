---
UID: NE.usb._USBD_ENDPOINT_OFFLOAD_MODE
title: USBD_ENDPOINT_OFFLOAD_MODE
author: windows-driver-content
description: Defines values for endpoint offloading options in the USB device or host controller.
old-location: buses\usbd_endpoint_offload_mode.htm
old-project: usbref
ms.assetid: 577B2B5E-934E-4354-B6FF-FDFE9D1144D7
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: URS_CONFIG, URS_CONFIG, *PURS_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: usb.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: USBD_ENDPOINT_OFFLOAD_MODE
req.alt-loc: Usb.h
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

# USBD_ENDPOINT_OFFLOAD_MODE enumeration



## -description
<p>Defines values for endpoint offloading options in the USB device or host controller.</p>


## -syntax

````
typedef enum _USBD_ENDPOINT_OFFLOAD_MODE { 
  UsbdEndpointOffloadModeNotSupported  = 0,
  UsbdEndpointOffloadSoftwareAssisted,
  UsbdEndpointOffloadHardwareAssisted
} USBD_ENDPOINT_OFFLOAD_MODE;
````


## -enum-fields
<dl>

### -field UsbdEndpointOffloadModeNotSupported

<dd>
<p>Endpoint offloading is not supported.</p>
</dd>

### -field UsbdEndpointOffloadSoftwareAssisted

<dd>
<p>Endpoint offloading is handled by the software.</p>
</dd>

### -field UsbdEndpointOffloadHardwareAssisted

<dd>
<p>Endpoint offloading is handled in the USB device or host controller hardware.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 10, version 1709</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2016</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Usb.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="buses.usbd_getcapability">USBD_QueryUsbCapability</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBD_ENDPOINT_OFFLOAD_MODE enumeration%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
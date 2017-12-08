---
UID: NF.wdfusb.WdfUsbInterfaceGetNumSettings
title: WdfUsbInterfaceGetNumSettings function
author: windows-driver-content
description: The WdfUsbInterfaceGetNumSettings method returns the number of alternate settings that a specified USB interface supports.
old-location: wdf\wdfusbinterfacegetnumsettings.htm
old-project: wdf
ms.assetid: 07de1b64-bafb-4b5b-8ef3-24b87ae0c273
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WdfUsbInterfaceGetNumSettings
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.5
req.umdf-ver: 2.0
req.alt-api: WdfUsbInterfaceGetNumSettings
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, UsbKmdfIrql, UsbKmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# WdfUsbInterfaceGetNumSettings function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]
The <b>WdfUsbInterfaceGetNumSettings</b> method returns the number of alternate settings that a specified USB interface supports.


## -syntax

````
BYTE WdfUsbInterfaceGetNumSettings(
  _In_ WDFUSBINTERFACE UsbInterface
);
````


## -parameters

### -param UsbInterface [in]

A handle to a USB interface object that was obtained by calling <a href="wdf.wdfusbtargetdevicegetinterface">WdfUsbTargetDeviceGetInterface</a>. 

## -returns
<b>WdfUsbInterfaceGetNumSettings</b> returns the number of alternate settings that the specified USB interface supports.

A bug check occurs if the driver supplies an invalid object handle.



## -remarks
Your driver can call <b>WdfUsbInterfaceGetNumSettings</b> after it has called <a href="wdf.wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a>.

For more information about the <b>WdfUsbInterfaceGetNumSettings</b> method and USB I/O targets, see <a href="wdf.usb_i_o_targets">USB I/O Targets</a>.

The following code example obtains the number of alternate settings that are available for a specified USB interface.

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
Minimum KMDF version
</th>
<td width="70%">
1.5
</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version
</th>
<td width="70%">
2.0
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdfusb.h (include Wdfusb.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (KMDF); </dt>
<dt>WUDFx02000.dll (UMDF)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;=DISPATCH_LEVEL
</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules
</th>
<td width="70%">
<a href="devtest.kmdf_drivercreate">DriverCreate</a>, <a href="devtest.kmdf_kmdfirql">KmdfIrql</a>, <a href="devtest.kmdf_kmdfirql2">KmdfIrql2</a>, <a href="devtest.kmdf_usbkmdfirql">UsbKmdfIrql</a>, <a href="devtest.kmdf_usbkmdfirql2">UsbKmdfIrql2</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a>
</dt>
<dt>
<a href="wdf.wdfusbtargetdevicegetinterface">WdfUsbTargetDeviceGetInterface</a>
</dt>
<dt>
<a href="wdf.wdfusbtargetdeviceselectconfig">WdfUsbTargetDeviceSelectConfig</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbInterfaceGetNumSettings method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
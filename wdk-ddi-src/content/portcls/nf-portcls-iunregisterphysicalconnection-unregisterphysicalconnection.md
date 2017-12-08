---
UID: NF.portcls.IUnregisterPhysicalConnection.UnregisterPhysicalConnection
title: IUnregisterPhysicalConnection::UnregisterPhysicalConnection
author: windows-driver-content
description: The UnregisterPhysicalConnection method deletes the registration of a physical connection that was registered by a previous call to PcRegisterPhysicalConnection.
old-location: audio\iunregisterphysicalconnection_unregisterphysicalconnection.htm
old-project: audio
ms.assetid: e8b99549-0fe2-4c8a-ad93-6689ebddee40
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: IUnregisterPhysicalConnection, UnregisterPhysicalConnection, IUnregisterPhysicalConnection::UnregisterPhysicalConnection
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IUnregisterPhysicalConnection.UnregisterPhysicalConnection
req.alt-loc: portcls.h
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
req.iface: IUnregisterPhysicalConnection
---

# IUnregisterPhysicalConnection::UnregisterPhysicalConnection method



## -description
<p>The <code>UnregisterPhysicalConnection</code> method deletes the registration of a physical connection that was registered by a previous call to <a href="..\portcls\nf-portcls-pcregisterphysicalconnection.md">PcRegisterPhysicalConnection</a>.</p>


## -syntax

````
NTSTATUS UnregisterPhysicalConnection(
  [in] PDEVICE_OBJECT DeviceObject,
  [in] PUNKNOWN       FromUnknown,
  [in] ULONG          FromPin,
  [in] PUNKNOWN       ToUnknown,
  [in] ULONG          ToPin
);
````


## -parameters
<dl>

### -param DeviceObject [in]

<dd>
<p>Pointer to the device object for the adapter device. This parameter must point to a system structure of type <a href="..\wdm\ns-wdm--device-object.md">DEVICE_OBJECT</a>.</p>
</dd>

### -param FromUnknown [in]

<dd>
<p>Pointer to the <a href="..\portcls\nn-portcls-iport.md">IPort</a> interface of a port driver object. The port driver object that is associated with <i>FromUnknown</i> is bound to the subdevice that supplies the connection's data source pin.</p>
</dd>

### -param FromPin [in]

<dd>
<p>Specifies a pin ID. This parameter identifies the data source (output) pin on the filter that is associated with the <i>FromUnknown</i> interface.</p>
</dd>

### -param ToUnknown [in]

<dd>
<p>Pointer to the <b>IPort</b> interface of a port driver object. The port driver object that is associated with <i>ToUnknown</i> is bound to the subdevice that supplies the connection's data sink pin.</p>
</dd>

### -param ToPin [in]

<dd>
<p>Specifies a pin ID. This parameter identifies the data sink (input) pin on the filter that is associated with the <i>ToUnknown</i> interface.</p>
</dd>
</dl>

## -returns
<p><code>UnregisterPhysicalConnection</code> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.</p>

## -remarks
<p>For more information, see <a href="https://msdn.microsoft.com/d8ebd6d9-37ed-4890-aae1-5ecf58f2e22a">Dynamic Audio Subdevices</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Portcls.h (include Portcls.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\portcls\nn-portcls-iunregisterphysicalconnection.md">IUnregisterPhysicalConnection</a>
</dt>
<dt>
<a href="..\portcls\nf-portcls-pcregisterphysicalconnection.md">PcRegisterPhysicalConnection</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm--device-object.md">DEVICE_OBJECT</a>
</dt>
<dt>
<a href="..\portcls\nn-portcls-iport.md">IPort</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IUnregisterPhysicalConnection::UnregisterPhysicalConnection method%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
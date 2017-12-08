---
UID: NF.hbaapi.HBA_GetBindingCapability
title: HBA_GetBindingCapability
author: windows-driver-content
description: The HBA_GetBindingCapability routine retrieves the binding capabilities of the indicated port.
old-location: storage\hba_getbindingcapability.htm
old-project: storage
ms.assetid: c4ac992a-7ef2-47b6-88d1-54b47b4a0af4
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: HBA_GetBindingCapability
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hbaapi.h
req.include-header: Hbaapi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HBA_GetBindingCapability
req.alt-loc: Hbaapi.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Hbaapi.lib
req.dll: Hbaapi.dll
req.irql: 
req.iface: 
---

# HBA_GetBindingCapability function



## -description
<p>The <b>HBA_GetBindingCapability</b> routine retrieves the binding capabilities of the indicated port. </p>


## -syntax

````
HBA_STATUS HBA_API HBA_GetBindingCapability(
  _In_  HBA_HANDLE          Handle,
  _In_  HBA_WWN             HbaPortWWN,
  _Out_ HBA_BIND_CAPABILITY *Flags
);
````


## -parameters
<dl>

### -param Handle [in]

<dd>
<p>Contains a value returned by the routine <a href="..\hbaapi\nf-hbaapi-hba-openadapter.md">HBA_OpenAdapter</a> that identifies the HBA on which the port is located. </p>
</dd>

### -param HbaPortWWN [in]

<dd>
<p>Contains a 64-bit worldwide name (WWN) that uniquely identifies the local HBA port whose persistent binding capabilities will be retrieved. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification.</p>
</dd>

### -param Flags [out]

<dd>
<p>Contains a bitwise OR of flags associated with the <a href="storage.hba_bind_type">HBA_BIND_TYPE</a> WMI property qualifier that represent the persistent binding capabilities of the port. </p>
</dd>
</dl>

## -returns
<p>The <b>HBA_GetBindingCapability</b> routine returns a value of type <a href="storage.hba_status">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_GetBindingCapability</b> returns one of the following qualifiers.</p><dl>
<dt><b>HBA_STATUS_ERROR_ILLEGAL_WWN</b></dt>
</dl><p>Returned if the adapter does not contain a port with the name <i>HbaPortWWN</i>. </p><dl>
<dt><b>HBA_STATUS_ERROR_NOT_SUPPORTED</b></dt>
</dl><p>Returned if the adapter does not support persistent bindings. </p><dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl><p>Returned if an unspecified error occurred that prevented the retrieval of the port attributes.</p>

<p> </p>

## -remarks


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
<dt>Hbaapi.h (include Hbaapi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Hbaapi.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>Hbaapi.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.hba_bind_type">HBA_BIND_TYPE</a>
</dt>
<dt>
<a href="..\hbaapi\nf-hbaapi-hba-openadapter.md">HBA_OpenAdapter</a>
</dt>
<dt>
<a href="storage.hba_status">HBA_STATUS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_GetBindingCapability routine%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
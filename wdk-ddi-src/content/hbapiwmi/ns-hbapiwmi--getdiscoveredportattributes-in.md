---
UID: NS.hbapiwmi._GetDiscoveredPortAttributes_IN
title: GetDiscoveredPortAttributes_IN
author: windows-driver-content
description: The GetDiscoveredPortAttributes_IN structure is used to pass input parameter data to the GetDiscoveredPortAttributes WMI method.
old-location: storage\getdiscoveredportattributes_in.htm
old-project: storage
ms.assetid: 99129f8e-c047-4e9f-bcaa-3cbcd2d30915
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: GetDiscoveredPortAttributes_IN, GetDiscoveredPortAttributes_IN, *PGetDiscoveredPortAttributes_IN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GetDiscoveredPortAttributes_IN
req.alt-loc: hbapiwmi.h
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

# GetDiscoveredPortAttributes_IN structure



## -description
<p>The GetDiscoveredPortAttributes_IN structure is used to pass input parameter data to the <a href="storage.getdiscoveredportattributes">GetDiscoveredPortAttributes</a> WMI method.</p>


## -syntax

````
typedef struct _GetDiscoveredPortAttributes_IN {
  ULONG PortIndex;
  ULONG DiscoveredPortIndex;
} GetDiscoveredPortAttributes_IN, *PGetDiscoveredPortAttributes_IN;
````


## -struct-fields
<dl>

### -field PortIndex

<dd>
<p>Indicates the index within the specified HBA of the port of type Nx_Port to query. For a definition of Nx_Port, see the T11 committee's specification for <i>Fibre Channel HBA API</i> (FC-HBA).</p>
</dd>

### -field DiscoveredPortIndex

<dd>
<p>Indicates the index within the specified HBA of the port of type FC_Port to query. For a definition of FC_Port, see the T11 committee's specification for <i>Fibre Channel HBA API</i> (FC-HBA).</p>
</dd>
</dl>

## -remarks
<p>The WMI tool suite generates a declaration of the GetDiscoveredPortAttributes_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="storage.msfc_hbaadaptermethods_wmi_class">MSFC_HBAAdapterMethods WMI Class</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Hbapiwmi.h (include Hbapiwmi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.getdiscoveredportattributes">GetDiscoveredPortAttributes</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20GetDiscoveredPortAttributes_IN structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
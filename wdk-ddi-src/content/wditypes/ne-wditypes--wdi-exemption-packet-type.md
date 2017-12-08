---
UID: NE.wditypes._WDI_EXEMPTION_PACKET_TYPE
title: WDI_EXEMPTION_PACKET_TYPE
author: windows-driver-content
description: The WDI_EXEMPTION_PACKET_TYPE enumeration defines the types of packet exemptions.
old-location: netvista\wdi_exemption_packet_type.htm
old-project: netvista
ms.assetid: 7F584EBE-9ACB-4AC7-9472-34322F24EF74
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WDF_WORKITEM_CONFIG, WDF_WORKITEM_CONFIG, *PWDF_WORKITEM_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wditypes.hpp
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WDI_EXEMPTION_PACKET_TYPE
req.alt-loc: wditypes.hpp
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# WDI_EXEMPTION_PACKET_TYPE enumeration



## -description
<p>The WDI_EXEMPTION_PACKET_TYPE enumeration defines the types of packet exemptions.</p>


## -syntax

````
typedef enum _WDI_EXEMPTION_PACKET_TYPE { 
  WDI_EXEMPT_PACKET_TYPE_UNICAST    = 1,
  WDI_EXEMPT_PACKET_TYPE_MULTICAST  = 2,
  WDI_EXEMPT_PACKET_TYPE_BOTH       = 3
} WDI_EXEMPTION_PACKET_TYPE;
````


## -enum-fields
<dl>

### -field WDI_EXEMPT_PACKET_TYPE_UNICAST

<dd>
<p>Exempt unicast packets only.</p>
</dd>

### -field WDI_EXEMPT_PACKET_TYPE_MULTICAST

<dd>
<p>Exempt multicast and broadcast packets only.</p>
</dd>

### -field WDI_EXEMPT_PACKET_TYPE_BOTH

<dd>
<p>Exempt all packet types.</p>
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
<p>Windows 10</p>
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
<dt>Wditypes.hpp</dt>
</dl>
</td>
</tr>
</table>
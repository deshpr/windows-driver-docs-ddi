---
UID: NS.ndiswwan._NDIS_WWAN_PRESHUTDOWN_STATE
title: NDIS_WWAN_PRESHUTDOWN_STATE
author: windows-driver-content
description: The NDIS_WWAN_PRESHUTDOWN_STATE structure contains the pre-shutdown status.
old-location: netvista\ndis_wwan_preshutdown_state.htm
old-project: netvista
ms.assetid: 39653A36-FFED-4F6A-9365-17E9D35DB46E
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: NDIS_WWAN_PRESHUTDOWN_STATE, NDIS_WWAN_PRESHUTDOWN_STATE, *PNDIS_WWAN_PRESHUTDOWN_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with  Windows 10, version 1511.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_WWAN_PRESHUTDOWN_STATE
req.alt-loc: ndiswwan.h
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
---

# NDIS_WWAN_PRESHUTDOWN_STATE structure



## -description
<p>The NDIS_WWAN_PRESHUTDOWN_STATE structure contains the pre-shutdown status.</p>


## -syntax

````
typedef struct _NDIS_WWAN_PRESHUTDOWN_STATE {
  NDIS_OBJECT_HEADER Header;
  WWAN_STATUS        uStatus;
} NDIS_WWAN_PRESHUTDOWN_STATE, *PNDIS_WWAN_PRESHUTDOWN_STATE;
````


## -struct-fields
<dl>

### -field Header

<dd>
<p>The header with type, revision, and size information about the NDIS_WWAN_PRESHUTDOWN_STATE
     structure. </p>
<table>
<tr>
<th>Header submember</th>
<th>Value</th>
</tr>
<tr>
<td>
<p>Type</p>
</td>
<td>
<p>NDIS_OBJECT_TYPE_DEFAULT</p>
</td>
</tr>
<tr>
<td>
<p>Revision</p>
</td>
<td>
<p> NDIS_WWAN_PRESHUTDOWN_STATE_REVISION_1</p>
</td>
</tr>
<tr>
<td>
<p>Size</p>
</td>
<td>
<p>sizeof(NDIS_WWAN_PRESHUTDOWN_STATE)</p>
</td>
</tr>
</table>
<p> </p>
<p>For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis--ndis-object-header.md">NDIS_OBJECT_HEADER</a>.</p>
</dd>

### -field uStatus

<dd>
<p>The following table shows the possible status codes.</p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<p>WWAN_STATUS_SUCCESS</p>
</td>
<td>
<p>Pre-shutdown operations are complete and the host can power down the MBB driver.</p>
</td>
</tr>
<tr>
<td>
<p>WWAN_STATUS_NO_DEVICE_SUPPORT</p>
</td>
<td>
<p>The modem does not support pre-shutdown notifications.</p>
</td>
</tr>
</table>
<p> </p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with  Windows 10, version 1511.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndiswwan.h (include Ndiswwan.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt593233">NDIS_STATUS_WWAN_PRESHUTDOWN_STATE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt593239">OID_WWAN_PRESHUTDOWN</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_PRESHUTDOWN_STATE structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
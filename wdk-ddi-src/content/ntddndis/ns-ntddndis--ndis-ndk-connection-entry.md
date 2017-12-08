---
UID: NS.ntddndis._NDIS_NDK_CONNECTION_ENTRY
title: NDIS_NDK_CONNECTION_ENTRY
author: windows-driver-content
description: The NDIS_NDK_CONNECTION_ENTRY structure specifies a connection entry for an active NDK connection on a miniport adapter.
old-location: netvista\ndis_ndk_connection_entry.htm
old-project: netvista
ms.assetid: 58BA2AE1-9F48-4B3B-A545-EECC9B3E858C
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: NDIS_NDK_CONNECTION_ENTRY, NDIS_NDK_CONNECTION_ENTRY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_NDK_CONNECTION_ENTRY
req.alt-loc: ntddndis.h
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

# NDIS_NDK_CONNECTION_ENTRY structure



## -description
<p>The <b>NDIS_NDK_CONNECTION_ENTRY</b> structure specifies a connection entry for an active NDK connection on a miniport adapter.</p>


## -syntax

````
typedef struct _NDIS_NDK_CONNECTION_ENTRY {
  SOCKADDR_INET Local;
  SOCKADDR_INET Remote;
  BOOLEAN       UserModeOwner;
  ULONG         OwnerPid;
} NDIS_NDK_CONNECTION_ENTRY, *PNDIS_NDK_CONNECTION_ENTRY;
````


## -struct-fields
<dl>

### -field Local

<dd>
<p>The local IP address and port.</p>
</dd>

### -field Remote

<dd>
<p>The remote IP address and port.</p>
</dd>

### -field UserModeOwner

<dd>
<p>A BOOLEAN value that is TRUE if the connection is an NDS user-mode connection, or FALSE if it is an NDK kernel-mode connection.</p>
</dd>

### -field OwnerPid

<dd>
<p>A process identifier for an NDS user-mode connection.</p>
</dd>
</dl>

## -remarks
<p>The NDIS_NDK_CONNECTION_ENTRY structure is used in the <a href="..\ntddndis\ns-ntddndis--ndis-ndk-connections.md">NDIS_NDK_CONNECTIONS</a> structure to specify an array of connections.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>None supported</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.30 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddndis\ns-ntddndis--ndis-ndk-connections.md">NDIS_NDK_CONNECTIONS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_NDK_CONNECTION_ENTRY structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
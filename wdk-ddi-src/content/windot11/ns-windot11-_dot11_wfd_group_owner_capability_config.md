---
UID: NS.WINDOT11._DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG
title: _DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG
author: windows-driver-content
description: the DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG structure is included with a OID_DOT11_WFD_GROUP_OWNER_CAPABILITY request. The structure contains capability settings for a Peer-to-Peer Group Owner (P2P GO).
old-location: netvista\_dot11_wfd_group_owner_capability_config.htm
old-project: netvista
ms.assetid: 6114799B-D0AC-421A-9F02-EED9A4391C03
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG, DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG, *PDOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Versions: Supported in Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG
req.alt-loc: Windot11.h
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
req.product: Windows 10 or later.
---

# _DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG structure



## -description

## -syntax

````
typedef struct _DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG {
  NDIS_OBJECT_HEADER Header;
  BOOLEAN            bPersistentGroupEnabled;
  BOOLEAN            bIntraBSSDistributionSupported;
  BOOLEAN            bCrossConnectionSupported;
  BOOLEAN            bPersistentReconnectSupported;
  BOOLEAN            bGroupFormationEnabled;
  ULONG              uMaximumGroupLimit;
}  DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG, *PDOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG;
````


## -struct-fields

### -field Header

Specifies the type, revision and size of the <b>DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG</b> structure. The required settings for the members of <b>Header</b> are the following:
<table>
<tr>
<th>Member</th>
<th>Setting</th>
</tr>
<tr>
<td><b>Type</b></td>
<td>NDIS_OBJECT_TYPE_DEFAULT</td>
</tr>
<tr>
<td><b>Revision</b></td>
<td>DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_WFD_GROUP_OWNER_CAPABILITY_CONFIG_1</td>
</tr>
</table>
 

### -field bPersistentGroupEnabled

If TRUE, the miniport must set the Persistent P2P Group bit of the Group Capability bitmask. Otherwise, the Persistent P2P Group bit must be cleared. The default value of this member is FALSE.

### -field bIntraBSSDistributionSupported

If TRUE, the miniport must set the Intra-BSS Distribution bit of the Group Capability bitmask. Otherwise, the Intra-BSS Distribution bit must be cleared. The default value of this member is FALSE.

### -field bCrossConnectionSupported

If TRUE, the miniport must set the Cross Connection bit of the Group Capability bitmask. Otherwise, the Cross Connection bit must be cleared. The default value of this member is FALSE.

### -field bPersistentReconnectSupported

If TRUE, the miniport must set the Persistent Reconnect bit of the Group Capability bitmask. Otherwise, the Persistent Reconnect bit must be cleared. The default value of this member is FALSE.

### -field bGroupFormationEnabled

If TRUE, the miniport must set the Group Formation bit of the Group Capability bitmask. Otherwise, the Group Formation bit must be cleared. The default value of this member is FALSE.

### -field uMaximumGroupLimit

Maximum number of P2P Clients the GO should allow. Once this limit is reached, the miniport should reject the addition of any new Clients and should set the Group Limit bit in the Group Capability bitmask. The default value for this member is same as the value reported in the  <b>uGORoleClientTableSize</b> member of <a href="netvista.dot11_wfd_attributes">DOT11_WFD_ATTRIBUTES</a>.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Versions: Supported in Windows 8
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Windot11.h (include Windot11.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451799">OID_DOT11_WFD_GROUP_OWNER_CAPABILITY</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20 DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
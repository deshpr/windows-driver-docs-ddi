---
UID: NS.fltuserstructures._INSTANCE_PARTIAL_INFORMATION
title: INSTANCE_PARTIAL_INFORMATION
author: windows-driver-content
description: The INSTANCE_PARTIAL_INFORMATION structure contains partial information for a minifilter instance.
old-location: ifsk\instance_partial_information.htm
old-project: ifsk
ms.assetid: cabcb39c-1f8d-41dc-a6ec-78f3fb3911cf
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: INSTANCE_PARTIAL_INFORMATION, INSTANCE_PARTIAL_INFORMATION, *PINSTANCE_PARTIAL_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: fltuserstructures.h
req.include-header: FltUser.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: INSTANCE_PARTIAL_INFORMATION
req.alt-loc: fltuserstructures.h
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

# INSTANCE_PARTIAL_INFORMATION structure



## -description
<p>The INSTANCE_PARTIAL_INFORMATION structure contains partial information for a minifilter instance. </p>


## -syntax

````
typedef struct _INSTANCE_PARTIAL_INFORMATION {
  ULONG  NextEntryOffset;
  USHORT InstanceNameLength;
  USHORT InstanceNameBufferOffset;
  USHORT AltitudeLength;
  USHORT AltitudeBufferOffset;
} INSTANCE_PARTIAL_INFORMATION, *PINSTANCE_PARTIAL_INFORMATION;
````


## -struct-fields
<dl>

### -field NextEntryOffset

<dd>
<p>Byte offset of the next INSTANCE_PARTIAL_INFORMATION entry, if multiple entries are present in a buffer. This member is zero if no other entries follow this one. </p>
</dd>

### -field InstanceNameLength

<dd>
<p>Length, in bytes, of the instance name. </p>
</dd>

### -field InstanceNameBufferOffset

<dd>
<p>Byte offset of the first character of the instance name string. This character is followed in memory by the remainder of the string. </p>
</dd>

### -field AltitudeLength

<dd>
<p>Length, in bytes, of the altitude string for the instance. </p>
</dd>

### -field AltitudeBufferOffset

<dd>
<p>Byte offset of the first character of the altitude string. This character is followed in memory by the remainder of the string. </p>
</dd>
</dl>

## -remarks
<p>This structure must be aligned on a LONGLONG (8-byte) boundary. If a buffer contains two or more of these structures, the <b>NextEntryOffset</b> value in each entry, except the last, falls on an 8-byte boundary. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Fltuserstructures.h (include FltUser.h or Fltkernel.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.filterattachataltitude">FilterAttachAtAltitude</a>
</dt>
<dt>
<a href="ifsk.filterinstancefindclose">FilterInstanceFindClose</a>
</dt>
<dt>
<a href="ifsk.filterinstancefindfirst">FilterInstanceFindFirst</a>
</dt>
<dt>
<a href="ifsk.filterinstancefindnext">FilterInstanceFindNext</a>
</dt>
<dt>
<a href="ifsk.filterinstancegetinformation">FilterInstanceGetInformation</a>
</dt>
<dt>
<a href="ifsk.filtervolumeinstancefindclose">FilterVolumeInstanceFindClose</a>
</dt>
<dt>
<a href="ifsk.filtervolumeinstancefindfirst">FilterVolumeInstanceFindFirst</a>
</dt>
<dt>
<a href="ifsk.filtervolumeinstancefindnext">FilterVolumeInstanceFindNext</a>
</dt>
<dt>
<a href="..\fltuserstructures\ns-fltuserstructures--instance-aggregate-standard-information.md">INSTANCE_AGGREGATE_STANDARD_INFORMATION</a>
</dt>
<dt>
<a href="..\fltuserstructures\ns-fltuserstructures--instance-basic-information.md">INSTANCE_BASIC_INFORMATION</a>
</dt>
<dt>
<a href="..\fltuserstructures\ns-fltuserstructures--instance-full-information.md">INSTANCE_FULL_INFORMATION</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20INSTANCE_PARTIAL_INFORMATION structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
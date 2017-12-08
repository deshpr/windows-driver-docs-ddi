---
UID: NS.ks.PKS_FRAMING_ITEM
title: PKS_FRAMING_ITEM
author: windows-driver-content
description: The KS_FRAMING_ITEM structure is used to declare allocator requirements on a kernel-mode pin.
old-location: stream\ks_framing_item.htm
old-project: stream
ms.assetid: cd7d4ef7-f8ad-467f-aa5b-28b131941094
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: PKS_FRAMING_ITEM, KS_FRAMING_ITEM, *PKS_FRAMING_ITEM
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KS_FRAMING_ITEM
req.alt-loc: ks.h
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

# PKS_FRAMING_ITEM structure



## -description
<p>The KS_FRAMING_ITEM structure is used to declare allocator requirements on a kernel-mode pin.</p>


## -syntax

````
typedef struct {
  GUID                      MemoryType;
  GUID                      BusType;
  ULONG                     MemoryFlags;
  ULONG                     BusFlags;
  ULONG                     Flags;
  ULONG                     Frames;
  ULONG                     FileAlignment;
  ULONG                     MemoryTypeWeight;
  KS_FRAMING_RANGE          PhysicalRange;
  KS_FRAMING_RANGE_WEIGHTED FramingRange;
} KS_FRAMING_ITEM, *PKS_FRAMING_ITEM;
````


## -struct-fields
<dl>

### -field MemoryType

<dd>
<p>Specifies the type of memory used for buffers and data frames. There is a partial correspondence between this member and the <b>PoolType</b> member in the <a href="stream.ksallocator_framing">KSALLOCATOR_FRAMING</a> structure. The two members differ in that <b>PoolType</b> allows only paged or nonpaged pool. <b>MemoryType</b> can have any of the values listed in the following table.</p>
<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
<p>KSMEMORY_TYPE_WILDCARD / KSMEMORY_TYPE_DONT_CARE / KSTYPE_DONT_CARE</p>
</td>
<td>
<p>Indicates memory allocation can be any type of memory.</p>
</td>
</tr>
<tr>
<td>
<p>KSMEMORY_TYPE_SYSTEM</p>
</td>
<td>
<p>Indicates memory allocation must be system memory.</p>
</td>
</tr>
<tr>
<td>
<p>KSMEMORY_TYPE_USER</p>
</td>
<td>
<p>Indicates memory allocation must be user-mode memory.</p>
</td>
</tr>
<tr>
<td>
<p>KSMEMORY_TYPE_KERNEL_PAGED</p>
</td>
<td>
<p>Indicates memory allocation must be kernel paged memory. This corresponds to the <b>PoolType</b> member of the <a href="stream.ksallocator_framing">KSALLOCATOR_FRAMING</a> structure set to <b>PagedPool</b> and the <b>RequirementsFlags</b> member of this structure set to SYSTEM_MEMORY.</p>
</td>
</tr>
<tr>
<td>
<p>KSMEMORY_TYPE_KERNEL_NONPAGED</p>
</td>
<td>
<p>Indicates memory allocation must be kernel nonpaged memory. This corresponds to the <b>PoolType</b> member of the <a href="stream.ksallocator_framing">KSALLOCATOR_FRAMING</a> structure set to <b>NonPagedPool</b> and the <b>RequirementsFlags</b> member of this structure set to SYSTEM_MEMORY.</p>
</td>
</tr>
<tr>
<td>
<p>KSMEMORY_TYPE_DEVICE_UNKNOWN</p>
</td>
<td>
<p>Indicates device memory allocation type is not specified.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -field BusType

<dd>
<p>Specifies the physical bus accessing the physical memory specified by <i>MemoryType</i>. Use this field to determine a compatible memory type based on the bus that is used for the connection medium. This distinction is crucial when a pin exposes different memory types based on the connection medium. <b>BusType</b> can have any of the values listed in the following table.</p>
<table>
<tr>
<th>Type</th>
<th>Description</th>
</tr>
<tr>
<td>
<p>GUID_BUS_TYPE_PCI</p>
</td>
<td>
<p>Peripheral component interconnect bus.</p>
</td>
</tr>
<tr>
<td>
<p>GUID_BUS_TYPE_USB</p>
</td>
<td>
<p>Universal serial bus.</p>
</td>
</tr>
<tr>
<td>
<p>GUID_BUS_TYPE_1394</p>
</td>
<td>
<p>IEEE 1394 serial bus.</p>
</td>
</tr>
<tr>
<td>
<p>GUID_BUS_TYPE_AVC</p>
</td>
<td>
<p>Audio/video control bus.</p>
</td>
</tr>
<tr>
<td>
<p>GUID_61883_CLASS</p>
</td>
<td>
<p>61883 protocol bus.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -field MemoryFlags

<dd>
<p>Specifies that the connection point is responsible for frame allocation. Should be set to KSALLOCATOR_REQUIREMENTF_MUST_ALLOCATE.</p>
</dd>

### -field BusFlags

<dd>
<p>Not used.  </p>
</dd>

### -field Flags

<dd>
<p>Similar to the <b>OptionsFlags</b> and <b>RequirementsFlags</b> union in the <a href="stream.ksallocator_framing">KSALLOCATOR_FRAMING</a> structure, with the addition of the following flags that add support for pipes.</p>
<dl>

### -field KSALLOCATOR_FLAG_PARTIAL_READ_SUPPORT (Indicates that the filter supports partial fill of frames.)


### -field KSALLOCATOR_FLAG_DEVICE_SPECIFIC (Indicates that the physical memory type is device-specific.)


### -field KSALLOCATOR_FLAG_CAN_ALLOCATE (Indicates that the filter is capable of allocating device-specific memory. See additional information below.)


### -field KSALLOCATOR_FLAG_INSIST_ON_FRAMESIZE_RATIO (Indicates that the frame ratio defined in the KS_COMPRESSION structure must be maintained.)


### -field KSALLOCATOR_REQUIREMENTF_PREFERENCES_ONLY (Indicates that the Requirements flags are preferences only and the connection point is able to allocate frames that do not meet those preferred specifications.)

</dl>
</dd>

### -field Frames

<dd>
<p>Specifies the total number of allowable outstanding frames. Corresponds to the <b>Frames</b> member of the <a href="stream.ksallocator_framing">KSALLOCATOR_FRAMING</a> structure.</p>
</dd>

### -field FileAlignment

<dd>
<p>Requirement for frame alignment. Corresponds to the <b>FileAlignment</b> member of the <a href="stream.ksallocator_framing">KSALLOCATOR_FRAMING</a> structure.</p>
</dd>

### -field MemoryTypeWeight

<dd>
<p>A value of type ULONG that specifies the pin-wide weight of this memory type.</p>
</dd>

### -field PhysicalRange

<dd>
<p>A structure of type <a href="stream.ks_framing_range">KS_FRAMING_RANGE</a> that specifies the physical limit of frame sizes.</p>
</dd>

### -field FramingRange

<dd>
<p>A structure of type <a href="stream.ks_framing_range_weighted">KS_FRAMING_RANGE_WEIGHTED</a> that specifies the optimal range of frame sizes.</p>
</dd>
</dl>

## -remarks
<p>Do not set KSALLOCATOR_FLAG_CAN_ALLOCATE to indicate memory addressing capability. A filter might be able to access the device-specific memory over a device-specific bus by referencing the memory address on this bus, and yet not support the protocol to allocate this device-specific memory.</p>

<p>Each <a href="stream.ksallocator_framing_ex">KSALLOCATOR_FRAMING_EX</a> instance contains one or more framing items.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.ksallocator_framing">KSALLOCATOR_FRAMING</a>
</dt>
<dt>
<a href="stream.ksallocator_framing_ex">KSALLOCATOR_FRAMING_EX</a>
</dt>
<dt>
<a href="stream.ks_framing_range">KS_FRAMING_RANGE</a>
</dt>
<dt>
<a href="stream.ks_framing_range_weighted">KS_FRAMING_RANGE_WEIGHTED</a>
</dt>
<dt>
<a href="stream.ks_compression">KS_COMPRESSION</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_FRAMING_ITEM structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
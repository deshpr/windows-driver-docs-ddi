---
UID: NS.wdm._CM_PARTIAL_RESOURCE_DESCRIPTOR
title: CM_PARTIAL_RESOURCE_DESCRIPTOR
author: windows-driver-content
description: The CM_PARTIAL_RESOURCE_DESCRIPTOR structure specifies one or more system hardware resources, of a single type, assigned to a device.
old-location: kernel\cm_partial_resource_descriptor.htm
old-project: kernel
ms.assetid: 96bf7bab-b8f5-439c-8717-ea6956ed0213
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: CM_PARTIAL_RESOURCE_DESCRIPTOR, CM_PARTIAL_RESOURCE_DESCRIPTOR, *PCM_PARTIAL_RESOURCE_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CM_PARTIAL_RESOURCE_DESCRIPTOR
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.iface: 
req.product: Windows 10 or later.
---

# CM_PARTIAL_RESOURCE_DESCRIPTOR structure



## -description
<p>The <b>CM_PARTIAL_RESOURCE_DESCRIPTOR</b> structure specifies one or more system hardware resources, of a single type, assigned to a device. This structure is used to create an array within a <a href="..\wdm\ns-wdm--cm-partial-resource-list.md">CM_PARTIAL_RESOURCE_LIST</a> structure.
   
  </p>


## -syntax

````
typedef struct _CM_PARTIAL_RESOURCE_DESCRIPTOR {
  UCHAR  Type;
  UCHAR  ShareDisposition;
  USHORT Flags;
  union {
    struct {
      PHYSICAL_ADDRESS Start;
      ULONG            Length;
    } Generic;
    struct {
      PHYSICAL_ADDRESS Start;
      ULONG            Length;
    } Port;
    struct {
#if defined(NT_PROCESSOR_GROUPS)
      USHORT    Level;
      USHORT    Group;
#else 
      ULONG     Level;
#endif 
      ULONG     Vector;
      KAFFINITY Affinity;
    } Interrupt;
    struct {
      union {
        struct {
#if defined(NT_PROCESSOR_GROUPS)
          USHORT    Group;
#else 
          USHORT    Reserved;
#endif 
          USHORT    MessageCount;
          ULONG     Vector;
          KAFFINITY Affinity;
        } Raw;
        struct {
#if defined(NT_PROCESSOR_GROUPS)
          USHORT    Level;
          USHORT    Group;
#else 
          ULONG     Level;
#endif 
          ULONG     Vector;
          KAFFINITY Affinity;
        } Translated;
      };
    } MessageInterrupt;
    struct {
      PHYSICAL_ADDRESS Start;
      ULONG            Length;
    } Memory;
    struct {
      ULONG Channel;
      ULONG Port;
      ULONG Reserved1;
    } Dma;
    struct {
      ULONG Channel;
      ULONG RequestLine;
      UCHAR TransferWidth;
      UCHAR Reserved1;
      UCHAR Reserved2;
      UCHAR Reserved3;
    } DmaV3;
    struct {
      ULONG Data[3];
    } DevicePrivate;
    struct {
      ULONG Start;
      ULONG Length;
      ULONG Reserved;
    } BusNumber;
    struct {
      ULONG DataSize;
      ULONG Reserved1;
      ULONG Reserved2;
    } DeviceSpecificData;
    struct {
      PHYSICAL_ADDRESS Start;
      ULONG            Length40;
    } Memory40;
    struct {
      PHYSICAL_ADDRESS Start;
      ULONG            Length48;
    } Memory48;
    struct {
      PHYSICAL_ADDRESS Start;
      ULONG            Length64;
    } Memory64;
    struct {
      UCHAR Class;
      UCHAR Type;
      UCHAR Reserved1;
      UCHAR Reserved2;
      ULONG IdLowPart;
      ULONG IdHighPart;
    } Connection;
  } u;
} CM_PARTIAL_RESOURCE_DESCRIPTOR, *PCM_PARTIAL_RESOURCE_DESCRIPTOR;
````


## -struct-fields
<dl>

### -field Type

<dd>
<p>Identifies the resource type. The constant value specified for <b>Type</b> indicates which structure within the <b>u</b> union is valid, as indicated in the following table. (These flags are used within both <b>CM_PARTIAL_RESOURCE_DESCRIPTOR</b> and <a href="..\wdm\ns-wdm--io-resource-descriptor.md">IO_RESOURCE_DESCRIPTOR</a> structures, except where noted.)</p>
<table>
<tr>
<th>Type value</th>
<th>u member substructure</th>
</tr>
<tr>
<td>
<p><b>CmResourceTypePort</b></p>
</td>
<td>
<p><b>u.Port</b></p>
</td>
</tr>
<tr>
<td>
<p><b>CmResourceTypeInterrupt</b></p>
</td>
<td><b>u.Interrupt</b> or <b>u.MessageInterrupt</b>.<p>If the CM_RESOURCE_INTERRUPT_MESSAGE flag of <b>Flags</b> is set, use <b>u.MessageInterrupt</b>; otherwise, use <b>u.Interrupt</b>.</p>
</td>
</tr>
<tr>
<td>
<p><b>CmResourceTypeMemory</b></p>
</td>
<td>
<p><b>u.Memory</b></p>
</td>
</tr>
<tr>
<td>
<p><b>CmResourceTypeMemoryLarge</b></p>
</td>
<td>One of <b>u.Memory40</b>, <b>u.Memory48</b>, or <b>u.Memory64</b>.<p>The CM_RESOURCE_MEMORY_LARGE_<i>XXX</i> flags set in the <b>Flags</b> member determines which structure is used.</p>
</td>
</tr>
<tr>
<td>
<p><b>CmResourceTypeDma</b></p>
</td>
<td>
<p><b>u.Dma</b>
          (if CM_RESOURCE_DMA_V3 is not set) or <b>u.DmaV3</b> (if CM_RESOURCE_DMA_V3 flag is set)</p>
</td>
</tr>
<tr>
<td>
<p><b>CmResourceTypeDevicePrivate</b></p>
</td>
<td>
<p><b>u.DevicePrivate</b></p>
</td>
</tr>
<tr>
<td>
<p><b>CmResourceTypeBusNumber</b></p>
</td>
<td>
<p><b>u.BusNumber</b></p>
</td>
</tr>
<tr>
<td>
<p><b>CmResourceTypeDeviceSpecific</b></p>
</td>
<td><b>u.DeviceSpecificData</b><p>(Not used within <b>IO_RESOURCE_DESCRIPTOR</b>.)</p>
</td>
</tr>
<tr>
<td>
<p><b>CmResourceTypePcCardConfig</b></p>
</td>
<td>
<p><b>u.DevicePrivate</b></p>
</td>
</tr>
<tr>
<td>
<p><b>CmResourceTypeMfCardConfig</b></p>
</td>
<td>
<p><b>u.DevicePrivate</b></p>
</td>
</tr>
<tr>
<td>
<p><b>CmResourceTypeConnection</b></p>
</td>
<td>
<p><b>u.Connection</b></p>
</td>
</tr>
<tr>
<td>
<p><b>CmResourceTypeConfigData</b></p>
</td>
<td>
<p><i>Reserved for system use.</i></p>
</td>
</tr>
<tr>
<td>
<p><b>CmResourceTypeNonArbitrated</b></p>
</td>
<td>
<p><i>
           Not used.</i></p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -field ShareDisposition

<dd>
<p>Indicates whether the described resource can be shared. Valid constant values are listed in the following table.</p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="CmResourceShareDeviceExclusive"></a><a id="cmresourcesharedeviceexclusive"></a><a id="CMRESOURCESHAREDEVICEEXCLUSIVE"></a><dl>

### -field CmResourceShareDeviceExclusive

</dl>
</td>
<td width="60%">
<p>The device requires exclusive use of the resource.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="CmResourceShareDriverExclusive"></a><a id="cmresourcesharedriverexclusive"></a><a id="CMRESOURCESHAREDRIVEREXCLUSIVE"></a><dl>

### -field CmResourceShareDriverExclusive

</dl>
</td>
<td width="60%">
<p>The driver requires exclusive use of the resource. (Not supported for WDM drivers.)</p>
</td>
</tr>
<tr>
<td width="40%"><a id="CmResourceShareShared"></a><a id="cmresourceshareshared"></a><a id="CMRESOURCESHARESHARED"></a><dl>

### -field CmResourceShareShared

</dl>
</td>
<td width="60%">
<p>The resource can be shared without restriction.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -field Flags

<dd>
<p>Contains flag bits that are specific to the resource type, as indicated in the following table. Flags can be bitwise-ORed together as appropriate.</p>
<table>
<tr>
<th>Resource type</th>
<th colspan="2">Flag</th>
<th>Definition</th>
</tr>
<tr>
<td colspan="4">
<p><b>CmResourceTypePort</b></p>
</td>
</tr>
<tr>
<td></td>
<td colspan="2">
<p>CM_RESOURCE_PORT_MEMORY</p>
</td>
<td>
<p>The device is accessed in memory address space.</p>
</td>
</tr>
<tr>
<td></td>
<td colspan="2">
<p>CM_RESOURCE_PORT_IO</p>
</td>
<td>
<p>The device is accessed in I/O address space.</p>
</td>
</tr>
<tr>
<td></td>
<td colspan="2">
<p>CM_RESOURCE_PORT_10_BIT_DECODE</p>
</td>
<td>
<p>The device decodes 10 bits of the port address.</p>
</td>
</tr>
<tr>
<td></td>
<td colspan="2">
<p>CM_RESOURCE_PORT_12_BIT_DECODE</p>
</td>
<td>
<p>The device decodes 12 bits of the port address.</p>
</td>
</tr>
<tr>
<td></td>
<td colspan="2">
<p>CM_RESOURCE_PORT_16_BIT_DECODE</p>
</td>
<td>
<p>The device decodes 16 bits of the port address.</p>
</td>
</tr>
<tr>
<td></td>
<td colspan="2">
<p>CM_RESOURCE_PORT_POSITIVE_DECODE</p>
</td>
<td>
<p>The device uses "positive decode" instead of "subtractive decode". (In general, PCI devices use positive decode and ISA buses use subtractive decode.)</p>
</td>
</tr>
<tr>
<td></td>
<td colspan="2">
<p>CM_RESOURCE_PORT_PASSIVE_DECODE</p>
</td>
<td>
<p>The device decodes the port but the driver does not use it.</p>
</td>
</tr>
<tr>
<td></td>
<td colspan="2">
<p>CM_RESOURCE_PORT_WINDOW_DECODE</p>
</td>
<td>
<p><u>Reserved for system use.
          </u></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b>CmResourceTypeInterrupt</b></p>
</td>
</tr>
<tr>
<td></td>
<td colspan="2">
<p>CM_RESOURCE_INTERRUPT_LEVEL_SENSITIVE</p>
</td>
<td>
<p>The IRQ line is level-triggered. (These IRQs are usually sharable.)</p>
</td>
</tr>
<tr>
<td></td>
<td colspan="2">
<p>CM_RESOURCE_INTERRUPT_LATCHED</p>
</td>
<td>
<p>The IRQ line is edge-triggered.</p>
</td>
</tr>
<tr>
<td></td>
<td colspan="2">
<p>CM_RESOURCE_INTERRUPT_MESSAGE</p>
</td>
<td>
<p>If this flag is set, the interrupt is a message-signaled interrupt. Otherwise, the interrupt is a line-based interrupt. This flag can be set starting with Windows Vista.</p>
</td>
</tr>
<tr>
<td></td>
<td colspan="2">
<p>CM_RESOURCE_INTERRUPT_POLICY_INCLUDED</p>
</td>
<td>
<p>Not used with the <b>CM_PARTIAL_RESOURCE_DESCRIPTOR</b> structure. For more information about this flag, see <a href="..\wdm\ns-wdm--io-resource-descriptor.md">IO_RESOURCE_DESCRIPTOR</a>.</p>
</td>
</tr>
<tr>
<td></td>
<td colspan="2">
<p>CM_RESOURCE_INTERRUPT_SECONDARY_INTERRUPT</p>
</td>
<td>
<p>The interrupt is a secondary interrupt. This flag can be set starting with Windows 8. For more information about secondary interrupts, see <a href="https://msdn.microsoft.com/0F56AD4C-E0BF-49F1-AB67-0107D08DEF9F">GPIO Interrupts</a>.</p>
</td>
</tr>
<tr>
<td></td>
<td colspan="2">
<p>CM_RESOURCE_INTERRUPT_WAKE_HINT</p>
</td>
<td>
<p>The interrupt is capable of waking the operating system from a low-power idle state or a system sleep state. This flag can be set starting with Windows 8. For more information about wake capabilities, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544239">Enabling Device Wake-Up</a>.</p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b>CmResourceTypeMemory</b></p>
</td>
</tr>
<tr>
<td></td>
<td colspan="2">
<p>CM_RESOURCE_MEMORY_READ_WRITE</p>
</td>
<td>
<p>The memory range is readable and writable.</p>
</td>
</tr>
<tr>
<td></td>
<td colspan="2">
<p>CM_RESOURCE_MEMORY_READ_ONLY</p>
</td>
<td>
<p>The memory range is read-only.</p>
</td>
</tr>
<tr>
<td></td>
<td colspan="2">
<p>CM_RESOURCE_MEMORY_WRITE_ONLY</p>
</td>
<td>
<p>The memory range is write-only.</p>
</td>
</tr>
<tr>
<td></td>
<td colspan="2">
<p>CM_RESOURCE_MEMORY_PREFETCHABLE</p>
</td>
<td>
<p>The memory range is prefetchable.</p>
</td>
</tr>
<tr>
<td></td>
<td colspan="2">
<p>CM_RESOURCE_MEMORY_COMBINEDWRITE</p>
</td>
<td>
<p>Combined-write caching is allowed.</p>
</td>
</tr>
<tr>
<td></td>
<td colspan="2">
<p>CM_RESOURCE_MEMORY_24</p>
</td>
<td>
<p>The device uses 24-bit addressing.</p>
</td>
</tr>
<tr>
<td></td>
<td colspan="2">
<p>CM_RESOURCE_MEMORY_CACHEABLE</p>
</td>
<td>
<p>The memory range is cacheable.</p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b>CmResourceTypeMemoryLarge</b></p>
</td>
</tr>
<tr>
<td></td>
<td>
<p>CM_RESOURCE_MEMORY_LARGE_40</p>
</td>
<td colspan="2">
<p>The memory descriptor uses the <b>u.Memory40</b> member.</p>
</td>
</tr>
<tr>
<td></td>
<td>
<p>CM_RESOURCE_MEMORY_LARGE_48</p>
</td>
<td colspan="2">
<p>The memory descriptor uses the <b>u.Memory48</b> member.</p>
</td>
</tr>
<tr>
<td></td>
<td>
<p>CM_RESOURCE_MEMORY_LARGE_64</p>
</td>
<td colspan="2">
<p>The memory descriptor uses the <b>u.Memory64</b> member.</p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b>CmResourceTypeDma</b></p>
</td>
</tr>
<tr>
<td></td>
<td colspan="2">
<p>CM_RESOURCE_DMA_8</p>
</td>
<td>
<p>8-bit DMA channel</p>
</td>
</tr>
<tr>
<td></td>
<td colspan="2">
<p>CM_RESOURCE_DMA_16</p>
</td>
<td>
<p>16-bit DMA channel</p>
</td>
</tr>
<tr>
<td></td>
<td colspan="2">
<p>CM_RESOURCE_DMA_32</p>
</td>
<td>
<p>32-bit DMA channel</p>
</td>
</tr>
<tr>
<td></td>
<td colspan="2">
<p>CM_RESOURCE_DMA_8_AND_16</p>
</td>
<td>
<p>8-bit and 16-bit DMA channel</p>
</td>
</tr>
<tr>
<td></td>
<td colspan="2">
<p>CM_RESOURCE_DMA_BUS_MASTER</p>
</td>
<td>
<p>The device supports bus master DMA transfers.</p>
</td>
</tr>
<tr>
<td></td>
<td colspan="2">
<p>CM_RESOURCE_DMA_TYPE_A</p>
</td>
<td>
<p>Type A DMA</p>
</td>
</tr>
<tr>
<td></td>
<td colspan="2">
<p>CM_RESOURCE_DMA_TYPE_B</p>
</td>
<td>
<p>Type B DMA</p>
</td>
</tr>
<tr>
<td></td>
<td colspan="2">
<p>CM_RESOURCE_DMA_TYPE_F</p>
</td>
<td>
<p>Type F DMA</p>
</td>
</tr>
<tr>
<td></td>
<td colspan="2">
<p>CM_RESOURCE_DMA_V3</p>
</td>
<td>
<p>Use the <b>DmaV3</b> member instead of the <b>Dma</b> member. The <b>DmaV3</b> member is available starting with Windows 8.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -field u

<dd>
<dl>

### -field Generic

<dd>
<p>Not used.</p>
</dd>

### -field Port

<dd>
<p>Specifies a range of I/O port addresses, using the following members.</p>
<p>Drivers for Windows Vista and later versions of the Windows operating system can use <a href="..\wdm\nf-wdm-rtlcmdecodememioresource.md">RtlCmDecodeMemIoResource</a> and <a href="..\wdm\nf-wdm-rtlcmencodememioresource.md">RtlCmEncodeMemIoResource</a> to read and update the <b>u.Port</b> member, rather than updating it directly.</p>
<dl>

### -field Start

<dd>
<p>For raw resources: Specifies the bus-relative physical address of the lowest of a range of contiguous I/O port addresses allocated to the device.</p>
<p>For translated resources: Specifies the system physical address of the lowest of a range of contiguous I/O port addresses allocated to the device.</p>
<p>For more information about raw and translated resources, see Remarks.</p>
</dd>

### -field Length

<dd>
<p>The length, in bytes, of the range of allocated I/O port addresses.</p>
</dd>
</dl>
</dd>

### -field Interrupt

<dd>
<p>Specifies an interrupt vector and level, using the following members:</p>
<dl>

### -field Level

<dd>
<p>For raw resources: Specifies the device's bus-specific IRQL (if appropriate for the platform and bus).</p>
<p>For translated resources: Specifies the DIRQL assigned to the device.</p>
<p>For more information about raw and translated resources, see Remarks.</p>
</dd>

### -field Group

<dd>
<p>Specifies the processor group number. This member exists only if the NT_PROCESSOR_GROUPS constant is defined at compile time. This member can be nonzero only on Windows 7 and later versions of Windows. The <b>Group</b> and <b>Affinity</b> members together specify a group affinity that indicates which processors the device can interrupt. To specify an affinity for any group, set <b>Group</b> to ALL_PROCESSOR_GROUPS.</p>
</dd>

### -field Vector

<dd>
<p>For raw resources: Specifies the device's bus-specific interrupt vector (if appropriate for the platform and bus).</p>
<p>For translated resources: Specifies the global system interrupt vector assigned to the device.</p>
<p>For more information about raw and translated resources, see Remarks.</p>
</dd>

### -field Affinity

<dd>
<p>Contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551830">KAFFINITY</a>-typed bitmask value indicating the set of processors the device can interrupt. To indicate that the device can interrupt any processor, this member is set to -1.</p>
</dd>
</dl>
</dd>

### -field MessageInterrupt

<dd>
<p>Specifies a message-signaled interrupt. This member is a union. Use <b>u.MessageInterrupt.Raw</b> for raw resources, and <b>u.MessageInterrupt.Translated</b> for translated resources. This type of resource is only returned on Windows Vista and later versions of the Windows operating system.</p>
<p>For more information about raw and translated resources, see Remarks.</p>
<p>The <b>u.MessageInterrupt.Raw</b> member has the following members:</p>
<dl>

### -field Raw

<dd>
<dl>

### -field Group

<dd>
<p>Specifies a processor group number. This member exists only if NT_PROCESSOR_GROUPS is defined at compile time. This member can be nonzero only on Windows 7 and later versions of Windows. The <b>Group</b> and <b>Affinity</b> members together specify a group affinity that indicates which processors can receive the device's interrupts. To specify an affinity for any group, set <b>Group</b> to ALL_PROCESSOR_GROUPS.</p>
</dd>

### -field Reserved

<dd>
<p>Not used.</p>
</dd>

### -field MessageCount

<dd>
<p>Specifies the number of message-signaled interrupts generated for this driver.</p>
</dd>

### -field Vector

<dd>
<p>Specifies the device's interrupt vector.</p>
</dd>

### -field Affinity

<dd>
<p>Specifies a KAFFINITY value that indicates the processors that receive the device's interrupts.</p>
</dd>
</dl>
</dd>

### -field Translated

<dd>
<p>The <b>u.MessageInterrupt.Translated</b> member has the following members:</p>
<dl>

### -field Level

<dd>
<p>Specifies the device IRQL (DIRQL) assigned to the device's interrupts.</p>
</dd>

### -field Group

<dd>
<p>Specifies a processor group number. This member exists only if NT_PROCESSOR_GROUPS is defined at compile time. This member can be nonzero only on Windows 7 and later versions of Windows. The <b>Translated.Group</b> and <b>Translated.Affinity</b> members together specify a group affinity that indicates which processors can receive the device's interrupts. To specify an affinity for any group, set <b>Translated.Group</b> to ALL_PROCESSOR_GROUPS.</p>
</dd>

### -field Level

<dd>
<p>Specifies the device IRQL (DIRQL) assigned to the device's interrupts.</p>
</dd>

### -field Vector

<dd>
<p>Specifies the device's interrupt vector.</p>
</dd>

### -field Affinity

<dd>
<p>Specifies a KAFFINITY value that identifies the processors that receive the device's interrupts.</p>
</dd>
</dl>
</dd>
</dl>
</dd>

### -field Memory

<dd>
<p>Specifies a range of memory addresses, using the following members.</p>
<p>Drivers for Windows Vista and later versions of the Windows operating system can use <a href="..\wdm\nf-wdm-rtlcmdecodememioresource.md">RtlCmDecodeMemIoResource</a> and <a href="..\wdm\nf-wdm-rtlcmencodememioresource.md">RtlCmEncodeMemIoResource</a> to read and update the <b>u.Memory</b> member, rather than updating it directly.</p>
<dl>

### -field Start

<dd>
<p>For raw resources: Specifies the bus-relative physical address of the lowest of a range of contiguous memory addresses allocated to the device.</p>
<p>For translated resources: Specifies the system physical address of the lowest of a range of contiguous memory addresses allocated to the device.</p>
<p>For more information about raw and translated resources, see Remarks.</p>
</dd>

### -field Length

<dd>
<p>Specifies the length, in bytes, of the range of allocated memory addresses.</p>
</dd>
</dl>
</dd>

### -field Dma

<dd>
<p>Specifies a DMA setting, using one of the following members:</p>
<dl>

### -field Channel

<dd>
<p>Specifies the number of the DMA channel on a system DMA controller that the device can use.</p>
</dd>

### -field Port

<dd>
<p>Specifies the number of the DMA port that an MCA-type device can use.</p>
</dd>

### -field Reserved1

<dd>
<p>Not used.</p>
</dd>
</dl>
</dd>

### -field DmaV3

<dd>
<p>Specifies the DMA settings for a driver that uses version 3 of the <a href="..\wdm\ns-wdm--dma-operations.md">DMA_OPERATIONS</a> structure.</p>
<p>The <b>u.DmaV3</b> member is available starting with Windows 8.</p>
<dl>

### -field Channel

<dd>
<p>Specifies the number of the DMA channel on the system DMA controller that is allocated to the device.</p>
</dd>

### -field RequestLine

<dd>
<p>Specifies the number of the request line on the system DMA controller that is allocated to the device.</p>
</dd>

### -field TransferWidth

<dd>
<p>Specifies the width, in bits, of the data bus that the system DMA controller that is allocated to the device uses to transfer data to or from the device.</p>
</dd>

### -field Reserved1

<dd>
<p>Not used.</p>
</dd>

### -field Reserved2

<dd>
<p>Not used.</p>
</dd>

### -field Reserved3

<dd>
<p>Not used.</p>
</dd>
</dl>
</dd>

### -field DevicePrivate

<dd>
<p>Reserved for system use.</p>
</dd>

### -field BusNumber

<dd>
<p>Specifies bus numbers, using the following members:</p>
<dl>

### -field Start

<dd>
<p>Specifies the lowest-numbered of a range of contiguous buses allocated to the device.</p>
</dd>

### -field Length

<dd>
<p>Specifies the number of buses allocated to the device.</p>
</dd>

### -field Reserved

<dd>
<p>Not used.</p>
</dd>
</dl>
</dd>

### -field DeviceSpecificData

<dd>
<p>Specifies the size of a device-specific, private structure that is appended to the end of the <b>CM_PARTIAL_RESOURCE_DESCRIPTOR</b> structure. If <b>u.DeviceSpecificData</b> is used, the <b>CM_PARTIAL_RESOURCE_DESCRIPTOR</b> structure must be the last one in the <a href="..\wdm\ns-wdm--cm-partial-resource-list.md">CM_PARTIAL_RESOURCE_LIST</a> array.</p>
<p>Examples of device-specific structures include <a href="..\wdm\ns-wdm--cm-floppy-device-data.md">CM_FLOPPY_DEVICE_DATA</a>, <a href="..\wdm\ns-wdm--cm-keyboard-device-data.md">CM_KEYBOARD_DEVICE_DATA</a>, <a href="..\wdm\ns-wdm--cm-scsi-device-data.md">CM_SCSI_DEVICE_DATA</a>, and <a href="..\wdm\ns-wdm--cm-serial-device-data.md">CM_SERIAL_DEVICE_DATA</a>.</p>
<dl>

### -field DataSize

<dd>
<p>Specifies the number of bytes appended to the end of the <b>CM_PARTIAL_RESOURCE_DESCRIPTOR</b> structure.</p>
</dd>

### -field Reserved1

<dd>
<p>Not used.</p>
</dd>

### -field Reserved2

<dd>
<p>Not used.</p>
</dd>
</dl>
</dd>

### -field Memory40

<dd>
<p>Specifies a range of memory addresses, using the following members.</p>
<p>The <b>u.Memory40</b> member is available only on Windows Vista and later versions of the Windows operating system. Drivers must use <a href="..\wdm\nf-wdm-rtlcmdecodememioresource.md">RtlCmDecodeMemIoResource</a> and <a href="..\wdm\nf-wdm-rtlcmencodememioresource.md">RtlCmEncodeMemIoResource</a> to read and update this member, rather than updating it directly.</p>
<dl>

### -field Start

<dd>
<p>For raw resources: Specifies the bus-relative physical address of the lowest of a range of contiguous memory addresses that are allocated to the device.</p>
<p>For translated resources: Specifies the system physical address of the lowest of a range of contiguous memory addresses that are allocated to the device.</p>
<p>For more information about raw and translated resources, see Remarks.</p>
</dd>

### -field Length40

<dd>
<p>Contains the high 32 bits of the 40-bit length, in bytes, of the range of allocated memory addresses. The lowest 8 bits are treated as zero.</p>
</dd>
</dl>
</dd>

### -field Memory48

<dd>
<p>Specifies a range of memory addresses, using the following members.</p>
<p>The <b>u.Memory48</b> member is available only on Windows Vista and later versions of the Windows operating system. Drivers must use <a href="..\wdm\nf-wdm-rtlcmdecodememioresource.md">RtlCmDecodeMemIoResource</a> and <a href="..\wdm\nf-wdm-rtlcmencodememioresource.md">RtlCmEncodeMemIoResource</a> to read and update this member, rather than updating it directly.</p>
<dl>

### -field Start

<dd>
<p>For raw resources: Specifies the bus-relative physical address of the lowest of a range of contiguous memory addresses that are allocated to the device.</p>
<p>For translated resources: Specifies the system physical address of the lowest of a range of contiguous memory addresses that are allocated to the device.</p>
<p>For more information about raw and translated resources, see Remarks.</p>
</dd>

### -field Length48

<dd>
<p>Contains the high 32 bits of the 48-bit length, in bytes, of the range of allocated memory addresses. The lowest 16 bits are treated as zero.</p>
</dd>
</dl>
</dd>

### -field Memory64

<dd>
<p>Specifies a range of memory addresses, using the following members.</p>
<p>The <b>u.Memory64</b> member is available only on Windows Vista and later versions of the Windows operating system. Drivers must use <a href="..\wdm\nf-wdm-rtlcmdecodememioresource.md">RtlCmDecodeMemIoResource</a> and <a href="..\wdm\nf-wdm-rtlcmencodememioresource.md">RtlCmEncodeMemIoResource</a> to read and update this member, rather than updating it directly.</p>
<dl>

### -field Start

<dd>
<p>For raw resources: Specifies the bus-relative physical address of the lowest of a range of contiguous memory addresses that are allocated to the device.</p>
<p>For translated resources: Specifies the system physical address of the lowest of a range of contiguous memory addresses that are allocated to the device.</p>
<p>For more information about raw and translated resources, see Remarks.</p>
</dd>

### -field Length64

<dd>
<p>Contains the high 32 bits of the 64-bit length, in bytes, of the range of allocated memory addresses. The lowest 32 bits are treated as zero.</p>
</dd>
</dl>
</dd>

### -field Connection

<dd>
<p>Specifies a connection to a <a href="https://msdn.microsoft.com/2c660e14-5b27-4610-a328-735b07ed0773">serial bus</a> or <a href="serports.extension_based_serial_controller_driver_design_guide">serial port</a>, or to a set of one or more <a href="https://msdn.microsoft.com/450E7F80-D9AC-4F52-8062-2DA5343C8D0F">general-purpose I/O</a> (GPIO) pins. The following members describe this connection.</p>
<p>The <b>u.Connection</b> member is available starting with Windows 8.</p>
<dl>

### -field Class

<dd>
<p>Specifies the connection class. This member is set to one of the following values.</p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="CM_RESOURCE_CONNECTION_CLASS_GPIO"></a><a id="cm_resource_connection_class_gpio"></a><dl>

### -field CM_RESOURCE_CONNECTION_CLASS_GPIO

</dl>
</td>
<td width="60%">
<p>Access the device through one or more pins on a GPIO controller.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="CM_RESOURCE_CONNECTION_CLASS_SERIAL"></a><a id="cm_resource_connection_class_serial"></a><dl>

### -field CM_RESOURCE_CONNECTION_CLASS_SERIAL

</dl>
</td>
<td width="60%">
<p>Access the device through a serial bus or serial port.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -field Type

<dd>
<p>Specifies the connection type.</p>
<p>If <b>Class</b> = CM_RESOURCE_CONNECTION_CLASS_GPIO, <b>Type</b> is set to the following value.</p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="CM_RESOURCE_CONNECTION_TYPE_GPIO_IO"></a><a id="cm_resource_connection_type_gpio_io"></a><dl>

### -field CM_RESOURCE_CONNECTION_TYPE_GPIO_IO

</dl>
</td>
<td width="60%">
<p>Access the device through GPIO pins that are configured for I/O.</p>
</td>
</tr>
</table>
<p> </p>
<div class="alert"><b>Note</b>  A GPIO pin that is configured as an interrupt request input is accessed as an ordinary interrupt resource (<b>CmResourceTypeInterrupt</b>).</div>
<div> </div>
<p>If <b>Class</b> = CM_RESOURCE_CONNECTION_CLASS_SERIAL, <b>Type</b> is set to one of the following values.</p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="CM_RESOURCE_CONNECTION_TYPE_SERIAL_I2C"></a><a id="cm_resource_connection_type_serial_i2c"></a><dl>

### -field CM_RESOURCE_CONNECTION_TYPE_SERIAL_I2C

</dl>
</td>
<td width="60%">
<p>The device is connected to an I²C bus.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="CM_RESOURCE_CONNECTION_TYPE_SERIAL_SPI"></a><a id="cm_resource_connection_type_serial_spi"></a><dl>

### -field CM_RESOURCE_CONNECTION_TYPE_SERIAL_SPI

</dl>
</td>
<td width="60%">
<p>The device is connected to an SPI bus.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="CM_RESOURCE_CONNECTION_TYPE_SERIAL_UART"></a><a id="cm_resource_connection_type_serial_uart"></a><dl>

### -field CM_RESOURCE_CONNECTION_TYPE_SERIAL_UART

</dl>
</td>
<td width="60%">
<p>The device is connected to a serial port.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -field Reserved1

<dd>
<p>Not used.</p>
</dd>

### -field Reserved2

<dd>
<p>Not used.</p>
</dd>

### -field IdLowPart

<dd>
<p>Contains the lower 32 bits of the 64-bit connection ID.</p>
</dd>

### -field IdHighPart

<dd>
<p>Contains the upper 32 bits of the 64-bit connection ID.</p>
</dd>
</dl>
</dd>
</dl>
</dd>
</dl>

## -remarks
<p>A <b>CM_PARTIAL_RESOURCE_DESCRIPTOR</b> structure can describe either a raw (bus-relative) resource or a translated (system physical) resource, depending on the routine or IRP with which it is being used. For more information, see <a href="kmdf.raw_and_translated_resources">Raw and Translated Resources</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\ns-wdm--cm-resource-list.md">CM_RESOURCE_LIST</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm--cm-full-resource-descriptor.md">CM_FULL_RESOURCE_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm--cm-partial-resource-list.md">CM_PARTIAL_RESOURCE_LIST</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm--cm-floppy-device-data.md">CM_FLOPPY_DEVICE_DATA</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm--cm-keyboard-device-data.md">CM_KEYBOARD_DEVICE_DATA</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm--cm-scsi-device-data.md">CM_SCSI_DEVICE_DATA</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm--cm-serial-device-data.md">CM_SERIAL_DEVICE_DATA</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm--dma-operations.md">DMA_OPERATIONS</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-ioconnectinterrupt.md">IoConnectInterrupt</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iogetdeviceproperty.md">IoGetDeviceProperty</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-ioreportresourcefordetection.md">IoReportResourceForDetection</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm--io-resource-descriptor.md">IO_RESOURCE_DESCRIPTOR</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551830">KAFFINITY</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlcmdecodememioresource.md">RtlCmDecodeMemIoResource</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlcmencodememioresource.md">RtlCmEncodeMemIoResource</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20CM_PARTIAL_RESOURCE_DESCRIPTOR structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
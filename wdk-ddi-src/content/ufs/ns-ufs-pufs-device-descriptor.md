---
UID: NS.ufs.PUFS_DEVICE_DESCRIPTOR
title: PUFS_DEVICE_DESCRIPTOR
author: windows-driver-content
description: UFS_DEVICE_DESCRIPTOR is the main descriptor for Universal Flash Storage (UFS) devices and should be the first descriptor retrieved as it specifies the device class and sub-class and the protocol (command set) to use to access this device and the maximum number of logical units contained within the device.
old-location: storage\ufs_device_descriptor.htm
old-project: storage
ms.assetid: CD1F59DA-3D84-422B-A862-8F4C5E1AA515
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: PUFS_DEVICE_DESCRIPTOR, UFS_DEVICE_DESCRIPTOR, *PUFS_DEVICE_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ufs.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UFS_DEVICE_DESCRIPTOR
req.alt-loc: Ufs.h
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
req.product: Windows 10 or later.
---

# PUFS_DEVICE_DESCRIPTOR structure



## -description
<p><b>UFS_DEVICE_DESCRIPTOR</b> is the main descriptor for Universal Flash Storage (UFS) devices and should be the first descriptor retrieved as it specifies the device class and sub-class and the protocol (command set) to use to access this device and the maximum number of logical
units contained within the device.</p>


## -syntax

````
typedef struct _UFS_DEVICE_DESCRIPTOR {
  UCHAR bLength;
  UCHAR bDescriptorIDN;
  UCHAR bDevice;
  UCHAR bDeviceClass;
  UCHAR bDeviceSubClass;
  UCHAR bProtocol;
  UCHAR  bNumberLU;
  UCHAR bNumberWLU;
  UCHAR bBootEnable;
  UCHAR bDescrAccessEn;
  UCHAR bInitPowerMode;
  UCHAR bHighPriorityLUN;
  UCHAR bSecureRemovalType;
  UCHAR bSecurityLU;
  UCHAR bBackgroundOpsTermLat;
  UCHAR bInitActiveICCLevel;
  UCHAR wSpecVersion[2];
  UCHAR wManufactureDate[2];
  UCHAR iManufacturerName;
  UCHAR iProductName;
  UCHAR iSerialNumberID;
  UCHAR iOemID;
  UCHAR wManufacturerID[2];
  UCHAR bUD0BaseOffset;
  UCHAR bUDConfigPLength;
  UCHAR bDeviceRTTCap;
  UCHAR wPeriodicRTCUpdate[2];
  UCHAR bUFSFeaturesSupport;
  UCHAR bFFUTimeout;
  UCHAR bQueueDepth;
  UCHAR wDeviceVersion[2];
  UCHAR bNumSecureWPArea;
  UCHAR dPSAMaxDataSize[4];
  UCHAR bPSAStateTimeout;
  UCHAR  iProductRevisionLevel;
  UCHAR Reserved[5];
  UCHAR Reserved2[16];
} UFS_DEVICE_DESCRIPTOR, *PUFS_DEVICE_DESCRIPTOR;
````


## -struct-fields
<dl>

### -field bLength

<dd>
<p>Specifies the length, in bytes, of this descriptor.</p>
</dd>

### -field bDescriptorIDN

<dd>
<p>Specifies the type of the descriptor. This descriptor will have a value of <b>UFS_DESC_DEVICE_IDN</b>.</p>
</dd>

### -field bDevice

<dd>
<p>Specifies the device type.</p>
<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>Device</td>
</tr>
<tr>
<td>All other values</td>
<td>Reserved for future use.</td>
</tr>
</table>
<p> </p>
</dd>

### -field bDeviceClass

<dd>
<p>Specifies the device class.</p>
<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>Mass Storage</td>
</tr>
<tr>
<td>All other values</td>
<td>Reserved for future use.</td>
</tr>
</table>
<p> </p>
</dd>

### -field bDeviceSubClass

<dd>
<p>Specifies the UFS mass storage subclasses in a bit map as follows:</p>
<table>
<tr>
<th>Bit</th>
<th>Value</th>
</tr>
<tr>
<td>0</td>
<td>Bootable / Non-Bootable</td>
</tr>
<tr>
<td>1</td>
<td>Embedded / Removable</td>
</tr>
<tr>
<td>2</td>
<td>Reserved for JESD220-1 (UME)</td>
</tr>
<tr>
<td>All other values</td>
<td>Reserved for future use.</td>
</tr>
</table>
<p> </p>
</dd>

### -field bProtocol

<dd>
<p>Specifies the protocol support by the UFS device.</p>
<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>SCSI</td>
</tr>
<tr>
<td>All other values</td>
<td>Reserved for future use.</td>
</tr>
</table>
<p> </p>
</dd>

### -field  bNumberLU

<dd>
<p>Specifies the number of Logical Units. This does not include the number of well known logical units.</p>
</dd>

### -field bNumberWLU

<dd>
<p>Specifies the number of well known logical units.</p>
</dd>

### -field bBootEnable

<dd>
<p>Specifies if a device's boot feature is enabled.</p>
<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>Boot feature disabled</td>
</tr>
<tr>
<td>0x01</td>
<td>Boot feature enabled</td>
</tr>
<tr>
<td>All other values</td>
<td>Reserved for future use.</td>
</tr>
</table>
<p> </p>
</dd>

### -field bDescrAccessEn

<dd>
<p>Indicates whether the Device Descriptor can be
read after the partial initialization phase of the
boot sequence.</p>
<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>Device Descriptor access disabled</td>
</tr>
<tr>
<td>0x01</td>
<td>Device Descriptor access enabled</td>
</tr>
<tr>
<td>All other values</td>
<td>Reserved for future use.</td>
</tr>
</table>
<p> </p>
</dd>

### -field bInitPowerMode

<dd>
<p><b>bInitPowerMode</b> defines the Power Mode
after device initialization or hardware reset.</p>
<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>UFS-Sleep mode</td>
</tr>
<tr>
<td>0x01</td>
<td>Active-mode</td>
</tr>
<tr>
<td>All other values</td>
<td>Reserved for future use.</td>
</tr>
</table>
<p> </p>
</dd>

### -field bHighPriorityLUN

<dd>
<p><b>bHighPriorityLUN</b> defines the high priority
logical unit.</p>
</dd>

### -field bSecureRemovalType

<dd>
<p>Specifies the secure removal type.</p>
<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>Information removed by an erase of the
physical memory</td>
</tr>
<tr>
<td>0x01</td>
<td>Information removed by overwriting the
addressed locations with a single character
followed by an erase.</td>
</tr>
<tr>
<td>0x02</td>
<td>Information removed by overwriting the
addressed locations with a character, its
complement, then a random character.</td>
</tr>
<tr>
<td>0x03</td>
<td>Information removed using a vendor
define mechanism.</td>
</tr>
<tr>
<td>All other values</td>
<td>Reserved for future use.</td>
</tr>
</table>
<p> </p>
</dd>

### -field bSecurityLU

<dd>
<p>Specifies if there is support for security LU's</p>
<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>Not supported</td>
</tr>
<tr>
<td>0x01</td>
<td>Replay Protected Memory Block (RPMB)</td>
</tr>
<tr>
<td>All other values</td>
<td>Reserved for future use.</td>
</tr>
</table>
<p> </p>
</dd>

### -field bBackgroundOpsTermLat

<dd>
<p><b>bBackgroundOpsTermLat</b> defines the maximum latency for starting data transmission when background
operations are ongoing. The termination latency limit applies to two cases:</p>
<ul>
<li>When the device receives a COMMAND UFS Protocol Information Units (UPIU) with a transfer request. The device shall start the data
transfer and send a DATA IN UPIU or a RTT UPIU within the latency limit.</li>
<li>When the device receives QUERY REQUEST UPIU to clear the <b>fBackgroundOpsEn</b> Flag. The device is
expected to terminate background operations within the latency limit.</li>
</ul>
</dd>

### -field bInitActiveICCLevel

<dd>
<p><b>bInitActiveICCLevel</b> defines the <b>bActiveICCLevel</b>
value after power on or reset. The range of the value is from 0x00 to 0x0F. </p>
</dd>

### -field wSpecVersion

<dd>
<p>Indicates the specification version in Binary Coded Decimal (BCD) format.</p>
</dd>

### -field wManufactureDate

<dd>
<p>Specifies the manufacturing date  in BCD format as 0xMMYY.</p>
</dd>

### -field iManufacturerName

<dd>
<p>Contains an index value to the string which contains the manufacturer's name.</p>
</dd>

### -field iProductName

<dd>
<p>Contains an index value to the string which contains the product's name.</p>
</dd>

### -field iSerialNumberID

<dd>
<p>Contains an index value to the string which contains the serial's number.</p>
</dd>

### -field iOemID

<dd>
<p>Contains an index value to the string which contains the OEM ID.</p>
</dd>

### -field wManufacturerID

<dd>
<p>Specifies the Manufacturer ID of the device.</p>
</dd>

### -field bUD0BaseOffset

<dd>
<p>Specifies the Offset of Unit Descriptor 0's configurable
parameters within the Configuration
Descriptor, <a href="storage.ufs_config_descriptor">UFS_CONFIG_DESCRIPTOR</a>.</p>
</dd>

### -field bUDConfigPLength

<dd>
<p>Total size of a <b>UFS_UNIT_CONFIG_DESCRIPTOR</b>'s
parameters.</p>
</dd>

### -field bDeviceRTTCap

<dd>
<p>Specifies the maximum number of outstanding READY TO TRANSFER UPIU'S
supported by device. The minimum value is 2.</p>
</dd>

### -field wPeriodicRTCUpdate

<dd>
<p>Specifies the frequency and method of real-time clock updates. Bits 10 to 15 are reserved.</p>
</dd>

### -field bUFSFeaturesSupport

<dd>
<p>Specifies which features are supported on this device. A feature is supported if its related bit is set to 1.</p>
<table>
<tr>
<th>Bit</th>
<th>Value</th>
</tr>
<tr>
<td>0</td>
<td>Field Firmware Update (FFU)</td>
</tr>
<tr>
<td>1</td>
<td>Production State Awarness (PSA)</td>
</tr>
<tr>
<td>2</td>
<td>Device Life Span</td>
</tr>
<tr>
<td>All other values</td>
<td>Reserved for future use.</td>
</tr>
</table>
<p> </p>
</dd>

### -field bFFUTimeout

<dd>
<p>The maximum time, in seconds, that access
to the device is limited or not possible through
any ports associated due to execution of a
WRITE BUFFER command.</p>
</dd>

### -field bQueueDepth

<dd>
<p>Specifies the queue depth. If this member is equal to 0, the device implements the per-LU
queuing architecture.</p>
</dd>

### -field wDeviceVersion

<dd>
<p>Specifies the device version.</p>
</dd>

### -field bNumSecureWPArea

<dd>
<p>Specifies the total number of
Secure Write Protect Areas supported by the
device. The value of this member is between <b>bNumberLU</b> and 32</p>
</dd>

### -field dPSAMaxDataSize

<dd>
<p>Specifies the maximum
amount of data that may be written during the
pre-soldering phase of the PSA flow.</p>
</dd>

### -field bPSAStateTimeout

<dd>
<p>Specifies the command
maximum timeout for a change in <b>bPSAState</b>. The timeout value is calculated as follows (in microseconds):</p>
<p>100 x 2 ^ <b>bPSAStateTimeout</b></p>
</dd>

### -field  iProductRevisionLevel

<dd>
<p>Specifies the index to the string which contains the Product
Revision Level.</p>
</dd>

### -field Reserved

<dd>
<p>Reserved for future use.</p>
</dd>

### -field Reserved2

<dd>
<p>Reserved for future use.</p>
</dd>
</dl>

## -remarks
<p>If <b>bBootEnable</b> in the <b>UFS_DEVICE_DESCRIPTOR</b> is set to zero or if the Boot well known logical unit is not mapped to an enabled logical unit, then the Boot well known logical unit shall terminate.</p>

<p><b>UFS_DEVICE_DESCRIPTOR</b> is read only, some of its parameters may be changed by changing the corresponding parameter in <a href="storage.ufs_unit_config_descriptor">UFS_UNIT_CONFIG_DESCRIPTOR</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 10, version 1709</p>
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
<dt>Ufs.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.ufs_unit_config_descriptor">UFS_UNIT_CONFIG_DESCRIPTOR</a>
</dt>
<dt>
<a href="storage.ufs_config_descriptor">UFS_CONFIG_DESCRIPTOR</a>
</dt>
<dt>
<a href="storage.ufs_geometry_descriptor">UFS_GEOMETRY_DESCRIPTOR</a>
</dt>
<dt>
<a href="storage.ufs_unit_descriptor">UFS_UNIT_DESCRIPTOR</a>
</dt>
<dt>
<a href="storage.ufs_rpmb_unit_descriptor">UFS_RPMB_UNIT_DESCRIPTOR</a>
</dt>
<dt>
<a href="storage.ufs_power_descriptor">UFS_POWER_DESCRIPTOR</a>
</dt>
<dt>
<a href="storage.ufs_interconnect_descriptor">UFS_INTERCONNECT_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\ufs\ns-ufs--ufs-string-descriptor.md">UFS_STRING_DESCRIPTOR</a>
</dt>
<dt>
<a href="storage.ufs_device_health_descriptor">UFS_DEVICE_HEALTH_DESCRIPTOR</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20UFS_DEVICE_DESCRIPTOR structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
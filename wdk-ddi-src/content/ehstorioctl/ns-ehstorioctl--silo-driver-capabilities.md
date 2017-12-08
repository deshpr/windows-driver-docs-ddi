---
UID: NS.ehstorioctl._SILO_DRIVER_CAPABILITIES
title: SILO_DRIVER_CAPABILITIES
author: windows-driver-content
description: This structure is used to specify the capabilities and support for IOCTL redirection of a storage silo driver. SILO_DRIVER_CAPABILITIES is included in the system buffer of an IOCTL_EHSTOR_DRIVER_REPORT_CAPABILITIES request.
old-location: storage\silo_driver_capabilities.htm
old-project: storage
ms.assetid: E2CD35A6-0FF2-4ABA-850E-12683C5F0D8D
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: SILO_DRIVER_CAPABILITIES, SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ehstorioctl.h
req.include-header: EhStorIoctl.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SILO_DRIVER_CAPABILITIES
req.alt-loc: EhStorIoctl.h
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

# SILO_DRIVER_CAPABILITIES structure



## -description
<p>This structure is used to specify the capabilities and support for IOCTL redirection of a storage silo driver. <b>SILO_DRIVER_CAPABILITIES</b> is included in the system buffer of an <a href="..\ehstorioctl\ni-ehstorioctl-ioctl-ehstor-driver-report-capabilities.md">IOCTL_EHSTOR_DRIVER_REPORT_CAPABILITIES</a> request.</p>


## -syntax

````
typedef struct _SILO_DRIVER_CAPABILITIES {
  ULONG StructSize;
  ULONG Capabilities;
  ULONG MaxLbaFilterCount;
  ULONG RedirectedIoctlListCount;
  ULONG RedirectedIoctlListOffset;
} SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES;
````


## -struct-fields
<dl>

### -field StructSize

<dd>
<p>The size of this structure. This is set to <b>sizeof</b>(SILO_DRIVER_CAPABILITIES).</p>
</dd>

### -field Capabilities

<dd>
<p>Capability flags for the silo driver. This is a bitwise OR combination of the following.</p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="CAP_ON_DEMAND_AUTHENTICATION"></a><a id="cap_on_demand_authentication"></a><dl>

### -field CAP_ON_DEMAND_AUTHENTICATION

</dl>
</td>
<td width="60%">
<p>The silo driver supports on-demand authentication and unauthentication.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="CAP_BANDING_SUPPORT"></a><a id="cap_banding_support"></a><dl>

### -field CAP_BANDING_SUPPORT

</dl>
</td>
<td width="60%">
<p>The silo driver supports banding of LBA ranges.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -field MaxLbaFilterCount

<dd>
<p>Maximum number of LBA filter entries the silo driver can provide in a <a href="..\ehstorioctl\ni-ehstorioctl-ioctl-ehstor-driver-update-lba-filter-table.md">IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE</a> request.</p>
</dd>

### -field RedirectedIoctlListCount

<dd>
<p>The number of redirected IOCTLs in the list following this structure.</p>
</dd>

### -field RedirectedIoctlListOffset

<dd>
<p>The offset of the redirected IOCTL list from the beginning of this structure. This will typically be <b>sizeof</b>(SILO_DRIVER_CAPABILITIES).</p>
</dd>
</dl>

## -remarks
<p>To support receiving <a href="..\ehstorioctl\ni-ehstorioctl-ioctl-ehstor-driver-perform-authz.md">IOCTL_EHSTOR_DRIVER_PERFORM_AUTHZ</a> from the enhanced storage class driver, a silo driver must set <b>CAP_ON_DEMAND_AUTHENTICATION</b> in <b>Capabilities</b>. Also, to support sending <a href="..\ehstorioctl\ni-ehstorioctl-ioctl-ehstor-driver-update-lba-filter-table.md">IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE</a>, a silo driver must set <b>CAP_BANDING_SUPPORT</b> in <b>Capabilities</b>.</p>

<p>To receive band management requests from the enhanced storage class driver, a silo driver must register a list of IOCTL codes it wants to receive. The redirected IOCTL list is an array of <b>ULONG</b> IOCTL codes with a length of <b>RedirectedIoctlListCount</b>. This list is included with the <b>SILO_DRIVER_CAPABILITIES</b> structure in the system buffer. The list is located in the system buffer following  <b>SILO_DRIVER_CAPABILITIES</b> at the offset indicated by <b>RedirectedIoctlListOffset</b>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows 8</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>EhStorIoctl.h (include EhStorIoctl.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ehstorioctl\ni-ehstorioctl-ioctl-ehstor-driver-perform-authz.md">IOCTL_EHSTOR_DRIVER_PERFORM_AUTHZ</a>
</dt>
<dt>
<a href="..\ehstorioctl\ni-ehstorioctl-ioctl-ehstor-driver-report-capabilities.md">IOCTL_EHSTOR_DRIVER_REPORT_CAPABILITIES</a>
</dt>
<dt>
<a href="..\ehstorioctl\ni-ehstorioctl-ioctl-ehstor-driver-update-lba-filter-table.md">IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SILO_DRIVER_CAPABILITIES structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
---
UID: NS.ntddk._SILO_MONITOR_REGISTRATION
title: SILO_MONITOR_REGISTRATION
author: windows-driver-content
description: This structure specifies a server silo monitor that can receive notifications about server silo events.
old-location: kernel\silo_monitor_registration.htm
old-project: kernel
ms.assetid: F99F6346-3FEE-4889-A058-C7540A4CBFC8
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: SILO_MONITOR_REGISTRATION, SILO_MONITOR_REGISTRATION, *PSILO_MONITOR_REGISTRATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SILO_MONITOR_REGISTRATION
req.alt-loc: ntddk.h
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

# SILO_MONITOR_REGISTRATION structure



## -description
<p>This structure specifies a server silo monitor that can receive notifications about server silo events.</p>


## -syntax

````
typedef struct _SILO_MONITOR_REGISTRATION {
  UCHAR                           Version;
  BOOLEAN                         MonitorHost;
  BOOLEAN                         MonitorExistingSilos;
  UCHAR                           Reserved[5];
  UNION {
    PUNICODE_STRING DriverObjectName;
    PUNICODE_STRING ComponentName;
  }                          DUMMYUNIONNAME;
  SILO_MONITOR_CREATE_CALLBACK    CreateCallback;
  SILO_MONITOR_TERMINATE_CALLBACK TerminateCallback;
} SILO_MONITOR_REGISTRATION, *PSILO_MONITOR_REGISTRATION;
````


## -struct-fields
<dl>

### -field Version

<dd>
<p>Set to <b>SERVER_SILO_MONITOR_REGISTRATION_VERSION</b>.</p>
</dd>

### -field MonitorHost

<dd>
<p>If <b>true</b>, a create notification will be delivered for the host context.</p>
</dd>

### -field MonitorExistingSilos

<dd>
<p>If <b>true</b>, create and terminate notifications will be delivered for any silos that currently exist at the time of registration; otherwise, only notifications for new silos will be delivered.</p>
</dd>

### -field Reserved

<dd>
<p>Reserved for system use.</p>
</dd>

### -field DUMMYUNIONNAME

<dd>
<p>Unnamed union.</p>
<dl>

### -field DriverObjectName

<dd>
<p>A pointer to the unicode name for the driver object registering for notifications.</p>
</dd>

### -field ComponentName

<dd>
<p>A pointer to the unicode name for the component registering for notifications.</p>
</dd>
</dl>
</dd>

### -field CreateCallback

<dd>
<p>A pointer to a callback that is invoked whenever a new server silo is created on the system.  This value may be <b>NULL</b>.  This gives drivers to opportunity to handle the event and set up per-silo data structures.</p>
</dd>

### -field TerminateCallback

<dd>
<p>A pointer to a callback that is invoked whenever a server silo is terminated (about to be destroyed) on the system.  This value may be <b>NULL</b>.  This gives drivers the opportunity to complete work within the silo and begin tearing down their per-silo data structures.</p>
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
<p>Windows 10, version 1607</p>
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
<dt>Ntddk.h</dt>
</dl>
</td>
</tr>
</table>
---
UID: NS.ucmmanager._UCM_MANAGER_CONFIG
title: UCM_MANAGER_CONFIG
author: windows-driver-content
description: Describes the configuration options for the UCM Manager. An initialized UCM_MANAGER_CONFIG structure is an input parameter value to UcmInitializeDevice.
old-location: buses\ucm_manager_config.htm
old-project: usbref
ms.assetid: 2B9539D7-6125-4912-9572-13FA7CA671D9
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: UCM_MANAGER_CONFIG, UCM_MANAGER_CONFIG, *PUCM_MANAGER_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucmmanager.h
req.include-header: Ucmcx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 2.15
req.alt-api: UCM_MANAGER_CONFIG
req.alt-loc: Ucmmanager.h
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
req.product: Windows 10 or later.
---

# UCM_MANAGER_CONFIG structure



## -description
<p>Describes the configuration options for the UCM Manager. An initialized <b>UCM_MANAGER_CONFIG</b> structure is an input parameter value to   <a href="..\ucmmanager\nf-ucmmanager-ucminitializedevice.md">UcmInitializeDevice</a>.</p>


## -syntax

````
typedef struct _UCM_MANAGER_CONFIG {
  ULONG                Size;
} UCM_MANAGER_CONFIG, *PUCM_MANAGER_CONFIG;
````


## -struct-fields
<dl>

### -field                Size

<dd>
<p>Size of the <b>UCM_MANAGER_CONFIG</b> structure. Initialize this structure by calling <a href="..\ucmmanager\nf-ucmmanager-ucm-manager-config-init.md">UCM_MANAGER_CONFIG_INIT</a>.</p>
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
<p>Minimum KMDF version</p>
</th>
<td width="70%">
<p>1.15</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>2.15</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ucmmanager.h (include Ucmcx.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ucmmanager\nf-ucmmanager-ucm-manager-config-init.md">UCM_MANAGER_CONFIG_INIT</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCM_MANAGER_CONFIG structure%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
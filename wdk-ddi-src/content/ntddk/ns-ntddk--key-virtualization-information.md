---
UID: NS.ntddk._KEY_VIRTUALIZATION_INFORMATION
title: KEY_VIRTUALIZATION_INFORMATION
author: windows-driver-content
description: The KEY_VIRTUALIZATION_INFORMATION structure defines the basic information that is available for a registry key or subkey.
old-location: kernel\key_virtualization_information.htm
old-project: kernel
ms.assetid: 128dd4ed-12c6-472a-b63c-d2d217b5c716
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: KEY_VIRTUALIZATION_INFORMATION, KEY_VIRTUALIZATION_INFORMATION, *PKEY_VIRTUALIZATION_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Available on Windows Vista and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KEY_VIRTUALIZATION_INFORMATION
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

# KEY_VIRTUALIZATION_INFORMATION structure



## -description
<p>The <b>KEY_VIRTUALIZATION_INFORMATION</b> structure defines the basic information that is available for a registry key or subkey. </p>


## -syntax

````
typedef struct _KEY_VIRTUALIZATION_INFORMATION {
  ULONG VirtualizationCandidate  :1;
  ULONG VirtualizationEnabled  :1;
  ULONG VirtualTarget  :1;
  ULONG VirtualStore  :1;
  ULONG VirtualSource  :1;
  ULONG Reserved  :27;
} KEY_VIRTUALIZATION_INFORMATION, *PKEY_VIRTUALIZATION_INFORMATION;
````


## -struct-fields
<dl>

### -field VirtualizationCandidate

<dd>
<p>Specifies whether the key is part of the virtualization namespace scope.</p>
</dd>

### -field VirtualizationEnabled

<dd>
<p>Specifies whether virtualization is enabled on this key. This value can be set to 1 only if <b>VirtualizationCandidate</b> is 1. </p>
</dd>

### -field VirtualTarget

<dd>
<p>Specifies whether the key is a virtual key. This value can be set to 1 only if <b>VirtualizationCandidate</b> and <b>VirtualizationEnabled</b> are both 0. This value is valid only on the virtual store key handles.</p>
</dd>

### -field VirtualStore

<dd>
<p>Specified whether the key is a part of the virtual store path.</p>
</dd>

### -field VirtualSource

<dd>
<p>Specifies whether the key has ever been virtualized. This value can be set to 1 only if <b>VirtualizationCandidate</b> is 1. </p>
</dd>

### -field Reserved

<dd>
<p>This value is reserved for system use. </p>
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
<p>Available on Windows Vista and later versions of the Windows operating system.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\ns-wdm--key-basic-information.md">KEY_BASIC_INFORMATION</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk--key-cached-information.md">KEY_CACHED_INFORMATION</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm--key-full-information.md">KEY_FULL_INFORMATION</a>
</dt>
<dt>
<a href="..\wdm\ne-wdm--key-information-class.md">KEY_INFORMATION_CLASS</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk--key-name-information.md">KEY_NAME_INFORMATION</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm--key-node-information.md">KEY_NODE_INFORMATION</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwenumeratekey.md">ZwEnumerateKey</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwquerykey.md">ZwQueryKey</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KEY_VIRTUALIZATION_INFORMATION structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
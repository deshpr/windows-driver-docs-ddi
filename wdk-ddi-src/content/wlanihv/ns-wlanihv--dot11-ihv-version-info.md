---
UID: NS.wlanihv._DOT11_IHV_VERSION_INFO
title: DOT11_IHV_VERSION_INFO
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_ihv_version_info.htm
old-project: netvista
ms.assetid: d482abdc-c6c1-4789-a1fc-39e76c32e78a
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: DOT11_IHV_VERSION_INFO,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wlanihv.h
req.include-header: Wlanihv.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_IHV_VERSION_INFO
req.alt-loc: wlanihv.h
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

# DOT11_IHV_VERSION_INFO structure



## -description

## -syntax

````
typedef struct _DOT11_IHV_VERSION_INFO {
  DWORD dwVerMin;
  DWORD dwVerMax;
} DOT11_IHV_VERSION_INFO, *PDOT11_IHV_VERSION_INFO;
````


## -struct-fields
<dl>

### -field dwVerMin

<dd>
<p>The minimum API version supported by the IHV Extensions DLL.
     </p>
<p>For the Windows Vista operating system, the minimum API version is zero.</p>
</dd>

### -field dwVerMax

<dd>
<p>The maximum API version supported by the IHV Extensions DLL.
     </p>
<p>For the Windows Vista operating system, the maximum API version is zero.</p>
</dd>
</dl>

## -remarks
<p>Prior to starting the IHV Extensions DLL through a call to the 
    <a href="..\wlanihv\nc-wlanihv-dot11extihv-init-service.md">Dot11ExtIhvInitService</a> IHV
    handler function, the operating system queries the API versions supported by the IHV Extensions DLL
    through a call to the 
    <a href="..\wlanihv\nc-wlanihv-dot11extihv-get-version-info.md">Dot11ExtIhvGetVersionInfo</a> IHV
    handler function. The IHV Extensions DLL returns the range of API versions it supports through the 
    <i>pDot11IHVVersionInfo</i> parameter.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating
   systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wlanihv.h (include Wlanihv.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv-get-version-info.md">Dot11ExtIhvGetVersionInfo</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv-init-service.md">Dot11ExtIhvInitService</a>
</dt>
<dt>
<a href="netvista.native_802_11_ihv_handler_functions">Native 802.11 IHV Handler
   Functions</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_IHV_VERSION_INFO structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
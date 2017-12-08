---
UID: NC.wsk.PFN_WSK_FREE_ADDRESS_INFO
title: PFN_WSK_FREE_ADDRESS_INFO
author: windows-driver-content
description: The WskFreeAddressInfo function frees address information that the WskGetAddressInfo function has dynamically allocated.
old-location: netvista\wskfreeaddressinfo.htm
old-project: netvista
ms.assetid: 552b4024-03d3-4e9b-b149-cf584c7e7259
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WPP_TRIAGE_INFO, WPP_TRIAGE_INFO, *PWPP_TRIAGE_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WskFreeAddressInfo
req.alt-loc: wsk.h
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

# PFN_WSK_FREE_ADDRESS_INFO callback



## -description
<p>The 
  <b>WskFreeAddressInfo</b> function frees address information that the 
  <a href="..\wsk\nc-wsk-pfn-wsk-get-address-info.md">WskGetAddressInfo</a> function has dynamically
  allocated.</p>


## -prototype

````
VOID WSKAPI * WskFreeAddressInfo(
  _In_ PWSK_CLIENT  Client,
  _In_ PADDRINFOEXW AddrInfo
);
````


## -parameters
<dl>

### -param Client [in]

<dd>
<p>[in] A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571155">WSK_CLIENT</a> structure that was returned through
     the 
     <i>WskProviderNpi</i> parameter of the 
     <a href="..\wsk\nf-wsk-wskcaptureprovidernpi.md">
     WskCaptureProviderNPI</a> function.</p>
</dd>

### -param AddrInfo [in]

<dd>
<p>[in] A pointer to a linked list of one or more <a href="winsock.addrinfoex">ADDRINFOEXW</a> structures that contain response
     information about the host. This pointer was returned through the 
     <i>Result</i> parameter of the 
     <a href="..\wsk\nc-wsk-pfn-wsk-get-address-info.md">WskGetAddressInfo</a> function.
     </p>
<p>The <a href="winsock.addrinfoex">ADDRINFOEXW</a> structure is defined in the 
     Ws2def.h header file. It is identical to the 
     <a href="winsock.addrinfoex">addrinfoex</a> structure.</p>
<div class="alert"><b>Important</b>  The 
     Ws2def.h header file is automatically included in 
     Wsk.h. Do not use 
     Ws2def.h directly.</div>
<div> </div>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows 7 and later versions of the Windows operating
   systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wsk.h (include Wsk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff571155">WSK_CLIENT</a>
</dt>
<dt>
<a href="..\wsk\nf-wsk-wskcaptureprovidernpi.md">WskCaptureProviderNPI</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn-wsk-get-address-info.md">WskGetAddressInfo</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PFN_WSK_FREE_ADDRESS_INFO callback function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
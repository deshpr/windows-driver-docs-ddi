---
UID: NC.ndkpi.NDK_FN_GET_REMOTE_TOKEN_FROM_MR
title: NDK_FN_GET_REMOTE_TOKEN_FROM_MR
author: windows-driver-content
description: The NdkGetRemoteTokenFromMr (NDK_FN_GET_REMOTE_TOKEN_FROM_MR) function gets a memory token from a remote NDK memory region (MR).
old-location: netvista\ndk_fn_get_remote_token_from_mr.htm
old-project: netvista
ms.assetid: 272DB944-E772-4E98-8918-AE0CEE440E3E
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: NDIS_WWAN_VISIBLE_PROVIDERS, NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdkGetRemoteTokenFromMr
req.alt-loc: ndkpi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.iface: 
---

# NDK_FN_GET_REMOTE_TOKEN_FROM_MR callback



## -description
<p>The <i>NdkGetRemoteTokenFromMr</i> (<i>NDK_FN_GET_REMOTE_TOKEN_FROM_MR</i>) function gets a memory token from a remote NDK memory region (MR).</p>


## -prototype

````
NDK_FN_GET_REMOTE_TOKEN_FROM_MR NdkGetRemoteTokenFromMr;

UINT32 NdkGetRemoteTokenFromMr(
  _In_ NDK_MR *pNdkMr
)
{ ... }
````


## -parameters
<dl>

### -param pNdkMr [in]

<dd>
<p>A pointer to an NDK memory region (MR) object (<a href="..\ndkpi\ns-ndkpi--ndk-mr.md">NDK_MR</a>).</p>
</dd>
</dl>

## -returns
<p>The 
     <i>NdkGetRemoteTokenFromMr</i> function returns a local memory region token.</p>

## -remarks
<p><i>NdkGetRemoteTokenFromMr</i> can be called after an <i>NdkRegisterMr</i> (<a href="..\ndkpi\nc-ndkpi-ndk-fn-register-mr.md">NDK_FN_REGISTER_MR</a>) or <i>NdkInitializeFastRegisterMr</i> (<a href="..\ndkpi\nc-ndkpi-ndk-fn-initialize-fast-register-mr.md">NDK_FN_INITIALIZE_FAST_REGISTER_MR</a>)  call is completed.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>None supported</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.30 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndkpi.h (include Ndkpi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;=DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk-fn-initialize-fast-register-mr.md">NDK_FN_INITIALIZE_FAST_REGISTER_MR</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk-fn-register-mr.md">NDK_FN_REGISTER_MR</a>
</dt>
<dt>
<a href="..\ndkpi\ns-ndkpi--ndk-mr.md">NDK_MR</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_GET_REMOTE_TOKEN_FROM_MR callback function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
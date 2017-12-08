---
UID: NS.ndkpi._NDK_QP_DISPATCH
title: NDK_QP_DISPATCH
author: windows-driver-content
description: The NDK_QP_DISPATCH structure specifies dispatch function entry points for the NDK queue pair (QP) object.
old-location: netvista\ndk_qp_dispatch.htm
old-project: netvista
ms.assetid: C2B50C94-693A-48A2-8458-5722F652C933
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: NDK_QP_DISPATCH, NDK_QP_DISPATCH
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDK_QP_DISPATCH
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

# NDK_QP_DISPATCH structure



## -description
<p>The <b>NDK_QP_DISPATCH</b> structure specifies dispatch function entry points for the NDK queue pair (QP) object.</p>


## -syntax

````
typedef struct _NDK_QP_DISPATCH {
  NDK_FN_CLOSE_OBJECT              NdkCloseQp;
  NDK_FN_QUERY_EXTENSION_INTERFACE NdkQueryExtension;
  NDK_FN_FLUSH                     NdkFlush;
  NDK_FN_SEND                      NdkSend;
  NDK_FN_RECEIVE                   NdkReceive;
  NDK_FN_BIND                      NdkBind;
  NDK_FN_FAST_REGISTER             NdkFastRegister;
  NDK_FN_INVALIDATE                NdkInvalidate;
  NDK_FN_READ                      NdkRead;
  NDK_FN_WRITE                     NdkWrite;
  NDK_FN_SEND_AND_INVALIDATE       NdkSendAndInvalidate;
} NDK_QP_DISPATCH;
````


## -struct-fields
<dl>

### -field NdkCloseQp

<dd>
<p>The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk-fn-close-object.md">NDK_FN_CLOSE_OBJECT</a> dispatch function.</p>
</dd>

### -field NdkQueryExtension

<dd>
<p>The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk-fn-query-extension-interface.md">NDK_FN_QUERY_EXTENSION_INTERFACE</a> dispatch function.</p>
</dd>

### -field NdkFlush

<dd>
<p>The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk-fn-flush.md">NDK_FN_FLUSH</a> dispatch function.</p>
</dd>

### -field NdkSend

<dd>
<p>The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk-fn-send.md">NDK_FN_SEND</a> dispatch function.</p>
</dd>

### -field NdkReceive

<dd>
<p>The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk-fn-receive.md">NDK_FN_RECEIVE</a> dispatch function.</p>
</dd>

### -field NdkBind

<dd>
<p>The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk-fn-bind.md">NDK_FN_BIND</a> dispatch function.</p>
</dd>

### -field NdkFastRegister

<dd>
<p>The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk-fn-fast-register.md">NDK_FN_FAST_REGISTER</a> dispatch function.</p>
</dd>

### -field NdkInvalidate

<dd>
<p>The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk-fn-invalidate.md">NDK_FN_INVALIDATE</a> dispatch function.</p>
</dd>

### -field NdkRead

<dd>
<p>The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk-fn-read.md">NDK_FN_READ</a> dispatch function.</p>
</dd>

### -field NdkWrite

<dd>
<p>The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk-fn-write.md">NDK_FN_WRITE</a> dispatch function.</p>
</dd>

### -field NdkSendAndInvalidate

<dd>
<p>The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk-fn-send-and-invalidate.md">NDK_FN_SEND_AND_INVALIDATE</a> dispatch function.</p>
<p><b>Note</b>  This member is supported only in NDKPI 1.2 (Windows Server 2012 R2) and later.</p>
</dd>
</dl>

## -remarks
<p>The <b>NDK_QP_DISPATCH</b> structure is used in the <a href="..\ndkpi\ns-ndkpi--ndk-qp.md">NDK_QP</a> structure.</p>

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
</table>

## -see-also
<dl>
<dt>
<a href="..\ndkpi\ns-ndkpi--ndk-qp.md">NDK_QP</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk-fn-bind.md">NDK_FN_BIND</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk-fn-close-object.md">NDK_FN_CLOSE_OBJECT</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk-fn-fast-register.md">NDK_FN_FAST_REGISTER</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk-fn-flush.md">NDK_FN_FLUSH</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk-fn-invalidate.md">NDK_FN_INVALIDATE</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk-fn-query-extension-interface.md">NDK_FN_QUERY_EXTENSION_INTERFACE</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk-fn-receive.md">NDK_FN_RECEIVE</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk-fn-send.md">NDK_FN_SEND</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk-fn-read.md">NDK_FN_READ</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk-fn-write.md">NDK_FN_WRITE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_QP_DISPATCH structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
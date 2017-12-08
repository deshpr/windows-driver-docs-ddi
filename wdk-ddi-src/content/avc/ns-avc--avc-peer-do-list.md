---
UID: NS.avc._AVC_PEER_DO_LIST
title: AVC_PEER_DO_LIST
author: windows-driver-content
description: The AVC_PEER_DO_LIST describes all nonvirtual (peer) instances of avc.sys.
old-location: stream\avc_peer_do_list.htm
old-project: stream
ms.assetid: 5420df9b-35e7-49b4-97dc-a1d61623551c
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: AVC_PEER_DO_LIST, AVC_PEER_DO_LIST, *PAVC_PEER_DO_LIST
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: avc.h
req.include-header: Avc.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: AVC_PEER_DO_LIST
req.alt-loc: avc.h
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

# AVC_PEER_DO_LIST structure



## -description
<p>The AVC_PEER_DO_LIST describes all nonvirtual (peer) instances of <i>avc.sys</i>.</p>


## -syntax

````
typedef struct _AVC_PEER_DO_LIST {
  ULONG          Count;
  PDEVICE_OBJECT *Objects;
} AVC_PEER_DO_LIST, *PAVC_PEER_DO_LIST;
````


## -struct-fields
<dl>

### -field Count

<dd>
<p>Ignored on input. On output, set to the number of objects in the list. If zero, the caller must not attempt to dereference the <b>Objects</b> member (it is set to <b>NULL</b>).</p>
</dd>

### -field Objects

<dd>
<p>Ignored on input. On output (and if the <b>Count</b> member is not zero) <b>Objects</b> contains a pointer to a contiguous array of DEVICE_OBJECT pointers. The caller must release the reference held on each object (by using <b>ObDereferenceObject</b>), and free the memory containing the list (by using <b>ExFreePool</b>) when finished with it.</p>
</dd>
</dl>

## -remarks
<p>This structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554168">AVC_FUNCTION_PEER_DO_LIST</a> function code.</p>

<p>This structure is used only as a member inside the AVC_MULTIFUNC_IRB structure. It is not used by itself.</p>

<p>See <a href="https://msdn.microsoft.com/3b4ec139-ff01-40bd-8e29-92f554180585">How to Use Avc.sys</a> For information about building and sending an AV/C command.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Avc.h (include Avc.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\avc\ns-avc--avc-multifunc-irb.md">AVC_MULTIFUNC_IRB</a>
</dt>
<dt>
<a href="stream.avc_function">AVC_FUNCTION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554168">AVC_FUNCTION_PEER_DO_LIST</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20AVC_PEER_DO_LIST structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
---
UID: NF.ntifs.FsRtlCompleteRequest
title: FsRtlCompleteRequest
author: windows-driver-content
description: The FsRtlCompleteRequest macro completes an IRP with the specified status.
old-location: ifsk\fsrtlcompleterequest.htm
old-project: ifsk
ms.assetid: dd53d3c5-3a31-4ea9-9f16-0d1b9397f63e
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FsRtlCompleteRequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FsRtlCompleteRequest
req.alt-loc: ntifs.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.iface: 
---

# FsRtlCompleteRequest function



## -description
<p>The <b>FsRtlCompleteRequest</b> macro completes an IRP with the specified status.</p>


## -syntax

````
VOID FsRtlCompleteRequest(
  _In_ PIRP     Irp,
  _In_ NTSTATUS Status
);
````


## -parameters
<dl>

### -param Irp [in]

<dd>
<p>Pointer to the IRP to be completed.</p>
</dd>

### -param Status [in]

<dd>
<p>Status value to be returned for the IRP.</p>
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
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-iocompleterequest.md">IoCompleteRequest</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlCompleteRequest function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
---
UID: NS.ntifs._FSRTL_PER_STREAM_CONTEXT
title: FSRTL_PER_STREAM_CONTEXT
author: windows-driver-content
description: The FSRTL_PER_STREAM_CONTEXT structure contains context information that a file system filter driver maintains about a file stream.
old-location: ifsk\fsrtl_per_stream_context.htm
old-project: ifsk
ms.assetid: 108c224c-ae42-414f-951d-cb225059d525
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FSRTL_PER_STREAM_CONTEXT, FSRTL_PER_STREAM_CONTEXT, *PFSRTL_PER_STREAM_CONTEXT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available on Microsoft Windows XP and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FSRTL_PER_STREAM_CONTEXT
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
req.irql: 
req.iface: 
---

# FSRTL_PER_STREAM_CONTEXT structure



## -description
<p>The <b>FSRTL_PER_STREAM_CONTEXT</b> structure contains context information that a file system filter driver maintains about a file stream. </p>


## -syntax

````
typedef struct _FSRTL_PER_STREAM_CONTEXT {
  LIST_ENTRY     Links;
  PVOID          OwnerId;
  PVOID          InstanceId;
  PFREE_FUNCTION FreeCallback;
} FSRTL_PER_STREAM_CONTEXT, *PFSRTL_PER_STREAM_CONTEXT;
````


## -struct-fields
<dl>

### -field Links

<dd>
<p>Link for this structure in the list of all per-stream context structures associated with the same file stream. <a href="..\ntifs\nf-ntifs-fsrtlinsertperstreamcontext.md">FsRtlInsertPerStreamContext</a> inserts this member into the list of all per-stream context structures for a file stream. To get a pointer to the head of the list from a file object, use the <a href="..\ntifs\nf-ntifs-fsrtlgetperstreamcontextpointer.md">FsRtlGetPerStreamContextPointer</a> macro, and cast the result to a <b>PFSRTL_ADVANCED_FCB_HEADER</b> pointer. The list pointer is the <b>FilterContexts</b> member in the advanced file control block (FCB) header structure for the file stream. </p>
</dd>

### -field OwnerId

<dd>
<p>Pointer to a filter-driver-allocated variable that uniquely identifies the owner of the per-stream context structure. The format of this variable is filter-driver-specific. Filter writers should choose a value that is both meaningful and convenient, such as the address of a driver object or device object. Filter drivers must set this member to a non-<b>NULL</b> value. </p>
</dd>

### -field InstanceId

<dd>
<p>Pointer to a filter-driver-allocated variable that can be used to distinguish among per-stream context structures created by the same filter driver. The format of this variable is filter-driver-specific. Filter writers should choose a value that is both meaningful and convenient, such as the address of the stream context object for the file stream. (To get this address from a file object, use the <a href="..\ntifs\nf-ntifs-fsrtlgetperstreamcontextpointer.md">FsRtlGetPerStreamContextPointer</a> macro.) </p>
<p>This member is optional and can be <b>NULL</b>. </p>
</dd>

### -field FreeCallback

<dd>
<p>Pointer to a callback routine that frees the per-stream context structure. This routine and its parameters are defined as follows: </p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
(*PFREE_FUNCTION) (
     IN PVOID Buffer
     );</pre>
</td>
</tr>
</table></span></div>
<p></p>
<dl>

### -field Buffer

<dd>
<p>Pointer to the <b>FSRTL_PER_STREAM_CONTEXT</b> structure to free. </p>
</dd>
</dl>
</dd>
</dl>

## -remarks
<p>File system filter drivers can use a <b>FSRTL_PER_STREAM_CONTEXT</b> structure to maintain context information for a file stream. This structure can be used as is or embedded in a driver-defined, per-stream context structure. </p>

<p>When a file system tears down the stream context object for a file stream, it must call <a href="..\ntifs\nf-ntifs-fsrtlteardownperstreamcontexts.md">FsRtlTeardownPerStreamContexts</a>, which in turn calls the <i>FreeCallback</i> routines of all per-stream context structures associated with the file stream. </p>

<p>The <b>FSRTL_PER_STREAM_CONTEXT</b> structure can be allocated from paged or nonpaged pool. </p>

<p>The <b>FsRtlSupportsPerStreamContexts</b> macro determines whether a file system supports per-stream contexts for a given file stream. </p>

<p>Parameters</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>This structure is available on Microsoft Windows XP and later.</p>
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
</table>

## -see-also
<dl>
<dt>
<a href="..\ntifs\ns-ntifs--fsrtl-advanced-fcb-header.md">FSRTL_ADVANCED_FCB_HEADER</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs--fsrtl-common-fcb-header.md">FSRTL_COMMON_FCB_HEADER</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-fsrtlgetperstreamcontextpointer.md">FsRtlGetPerStreamContextPointer</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-fsrtlinsertperstreamcontext.md">FsRtlInsertPerStreamContext</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-fsrtllookupperstreamcontext.md">FsRtlLookupPerStreamContext</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-fsrtlremoveperstreamcontext.md">FsRtlRemovePerStreamContext</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-fsrtlteardownperstreamcontexts.md">FsRtlTeardownPerStreamContexts</a>
</dt>
<dt>
<a href="ifsk.pfree_function">PFREE_FUNCTION</a>
</dt>
<dt>
<a href="ifsk.tracking_per_stream_context_in_a_legacy_file_system_filter_driver">Tracking Per-Stream Context in a Legacy File System Filter Driver</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FSRTL_PER_STREAM_CONTEXT structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
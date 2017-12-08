---
UID: NF.extsfns.IDebugFailureAnalysis2.GetNext
title: IDebugFailureAnalysis2::GetNext
author: windows-driver-content
description: The GetNext method searches a DebugFailureAnalysis object for the next FA entry, after a given FA entry, that satisfies conditions specified by the Tag and TagMask parameters.
old-location: debugger\idebugfailureanalysis2_getnext.htm
old-project: debugger
ms.assetid: 935E4BAD-2B4E-44DD-8AE6-A0FD1FE9F2BF
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugFailureAnalysis2, GetNext, IDebugFailureAnalysis2::GetNext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: extsfns.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugFailureAnalysis2.GetNext
req.alt-loc: extsfns.h
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
req.iface: IDebugFailureAnalysis2
---

# IDebugFailureAnalysis2::GetNext method



## -description
<p>   The <b>GetNext</b> method searches a <a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">DebugFailureAnalysis</a> object for the next <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a>, after a given FA entry, that satisfies conditions specified by the <i>Tag</i> and <i>TagMask</i> parameters.</p>


## -syntax

````
PFA_ENTRY GetNext(
  [in] PFA_ENTRY Entry,
  [in] FA_TAG    Tag,
  [in] FA_TAG    TagMask
);
````


## -parameters
<dl>

### -param Entry [in]

<dd>
<p>A pointer to an <a href="..\extsfns\ns-extsfns--fa-entry.md">FA_ENTRY</a> structure. The search starts after this <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a>. If this parameter is <b>NULL</b>, the starts at the beginning of the collection of FA entries.</p>
</dd>

### -param Tag [in]

<dd>
<p>A value in the <a href="https://msdn.microsoft.com/library/windows/hardware/jj991810">FA_TAG</a> enumeration.</p>
</dd>

### -param TagMask [in]

<dd>
<p>A mask that restricts the search to a subset of all possible tags. See Remarks. To search all possible tags, set this parameter to <b>DEBUG_FLR_MASK_ALL</b>.</p>
</dd>
</dl>

## -returns
<p>If the <a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">DebugFailureAnalysis</a> object has an <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a>, after the given entry, that satisfies the conditions, this method returns a pointer to the <a href="..\extsfns\ns-extsfns--fa-entry.md">FA_ENTRY</a> structure. Otherwise, this method returns <b>NULL</b>.</p>

## -remarks
<p>This method searches for an <a href="..\extsfns\ns-extsfns--fa-entry.md">FA_ENTRY</a> structure that satisfies this condition:</p>

<p>entry-&gt;Tag &amp; <i>TagMask</i> == <i>Tag</i></p>

<p>Tags are defined in extsfns.h as values of the <a href="..\extsfns\ne-extsfns--debug-flr-param-type.md">DEBUG_FLR_PARAM_TYPE</a> enumeration, which is also called the <a href="https://msdn.microsoft.com/library/windows/hardware/jj991810">FA_TAG</a> enumeration. The tags are arranged in groups so that you can use <i>TagMask</i> to search within a particular group. For example there is a group of tags related to pool errors. The numerical values assigned to the tags in this group are in the range 0x400, 0x401 ... 0x406. Every <a href="..\extsfns\ns-extsfns--fa-entry.md">FA_ENTRY</a> that has a tag in this group satisfies the following condition:</p>

<p><code>entry-&gt;Tag &amp; 0xFFFFFF00 == 0x400</code></p>

<p>The following code snippet shows a portion of the <a href="https://msdn.microsoft.com/library/windows/hardware/jj991810">FA_TAG</a> enumeration.</p>

<p><b>Example 1</b></p>

<p>The following example shows how to find all failure analysis entries that have a tag equal to <b>DEBUG_FLR_MANAGED_EXCEPTION_OBJECT</b>. Assume <code>pAnalysis</code> is a pointer to an <a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">IDebugFailureAnalysis2</a> interface.</p>

<p><b>Example 2</b></p>

<p>The following example shows how to find all FA entries that have tags in the Pool group. Recall the tags in the Pool group have values in the range 0x400, 0x401, ... 0x406. Assume <code>pAnalysis</code> is a pointer to an <a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">IDebugFailureAnalysis2</a> interface.</p>

<p><b>Example 3</b></p>

<p>You can create your own custom tags in the range 0xA0000001 through 0xAFFFFFFF.</p>

<p>The following example shows how to find all failure analysis entries that have custom tags. In other words, the code finds all entries with tags that satisfy this condition:</p>

<p><code>entry-&gt;Tag &amp; 0xF0000000 == 0xA0000000</code></p>

<p>Entries that have tags 0xA0000001, 0xA0000002, ... 0xAFFFFFF satisfy the condition. </p>

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
<dt>Extsfns.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">IDebugFailureAnalysis2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>
</dt>
<dt>
<a href="debugger.idebugfailureanalysis2_get">Get</a>
</dt>
<dt>
<a href="debugger.idebugfailureanalysis2_nextentry">NextEntry</a>
</dt>
<dt>
<a href="debugger._efn_analyze">_EFN_Analyze</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugFailureAnalysis2::GetNext method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
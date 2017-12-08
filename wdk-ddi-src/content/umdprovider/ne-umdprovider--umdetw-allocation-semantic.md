---
UID: NE.umdprovider._UMDETW_ALLOCATION_SEMANTIC
title: UMDETW_ALLOCATION_SEMANTIC
author: windows-driver-content
description: Indicates what a memory allocation is used for if the allocation is internal to the user-mode driver.
old-location: display\umdetw_allocation_semantic.htm
old-project: display
ms.assetid: 4c0fa5c1-7d73-4380-a673-f09bbf0ea281
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: UFX_PROPRIETARY_CHARGER, UFX_PROPRIETARY_CHARGER, *PUFX_PROPRIETARY_CHARGER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: umdprovider.h
req.include-header: Umdprovider.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UMDETW_ALLOCATION_SEMANTIC
req.alt-loc: umdprovider.h
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

# UMDETW_ALLOCATION_SEMANTIC enumeration



## -description
<p>Indicates what a memory allocation is used for if the allocation is internal to the user-mode driver.</p>


## -syntax

````
typedef enum _UMDETW_ALLOCATION_SEMANTIC { 
  UMDETW_ALLOCATION_SEMANTIC_NONE              = 0,
  UMDETW_ALLOCATION_SEMANTIC_DMA_BUFFER        = 1,
  UMDETW_ALLOCATION_SEMANTIC_UPLOAD_STAGING    = 2,
  UMDETW_ALLOCATION_SEMANTIC_DOWNLOAD_STAGING  = 3,
  UMDETW_ALLOCATION_SEMANTIC_CONTEXT_SAVE      = 4,
  UMDETW_ALLOCATION_SEMANTIC_DRIVER_OTHER_MIN  = 5,
  UMDETW_ALLOCATION_SEMANTIC_DRIVER_OTHER_MAX  = 0xFFFF
} UMDETW_ALLOCATION_SEMANTIC;
````


## -enum-fields
<dl>

### -field UMDETW_ALLOCATION_SEMANTIC_NONE

<dd>
<p>The allocation is created for a Direct3D resource.</p>
</dd>

### -field UMDETW_ALLOCATION_SEMANTIC_DMA_BUFFER

<dd>
<p>The allocation is used as a DMA buffer.</p>
</dd>

### -field UMDETW_ALLOCATION_SEMANTIC_UPLOAD_STAGING

<dd>
<p>The allocation is used as a staging allocation to upload and download data to and from video memory.</p>
</dd>

### -field UMDETW_ALLOCATION_SEMANTIC_DOWNLOAD_STAGING

<dd>
<p>The allocation is used exclusively as a staging allocation to download data from video memory.</p>
</dd>

### -field UMDETW_ALLOCATION_SEMANTIC_CONTEXT_SAVE

<dd>
<p>The allocation is used as a GPU context save area.</p>
</dd>

### -field UMDETW_ALLOCATION_SEMANTIC_DRIVER_OTHER_MIN

<dd>
<p>The driver can use this semantic value for its own internal purposes.</p>
</dd>

### -field UMDETW_ALLOCATION_SEMANTIC_DRIVER_OTHER_MAX

<dd>
<p>The driver can use this semantic value for its own internal purposes.</p>
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
<p>Windows 8</p>
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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Umdprovider.h (include Umdprovider.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\umdprovider\nf-umdprovider-umdetwlogmapallocation.md">UMDEtwLogMapAllocation</a>
</dt>
<dt>
<a href="..\umdprovider\nf-umdprovider-umdetwlogunmapallocation.md">UMDEtwLogUnmapAllocation</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20UMDETW_ALLOCATION_SEMANTIC enumeration%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
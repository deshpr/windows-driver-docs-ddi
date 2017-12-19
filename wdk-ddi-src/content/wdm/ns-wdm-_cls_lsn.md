---
UID: NS.WDM._CLS_LSN
title: _CLS_LSN
author: windows-driver-content
description: The CLFS_LSN structure identifies an individual record in a Common Log File System (CLFS) stream.
old-location: kernel\clfs_lsn.htm
old-project: kernel
ms.assetid: ac50c4e1-4b87-4c6e-a5c7-24f961224134
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _CLS_LSN, CLS_LSN, *PCLS_LSN, PPCLS_LSN, PCLS_LSN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CLS_LSN
req.alt-loc: wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.product: Windows 10 or later.
---

# _CLS_LSN structure



## -description
The <b>CLFS_LSN</b> structure identifies an individual record in a Common Log File System (CLFS) stream.



## -syntax

````
typedef struct _CLS_LSN {
  ULONGLONG Internal;
} CLS_LSN, *PCLS_LSN, **PPCLS_LSN, PCLFS_LSN, *PCLFS_LSN, **PPCLFS_LSN;
````


## -struct-fields

### -field Internal

A 64-bit value that holds three pieces of information about a log record: container identifier, block offset, and record sequence number. 


## -remarks
A container is a contiguous physical disk extent that serves as part of a CLFS log. A given CLFS log has several containers. Each container has several sector-aligned blocks, each of which holds a numbered sequence of records. A record can be identified by the triple (logical container identifier, block offset, record sequence number).

To obtain the container identifier, block offset, and record sequence number from a <b>CLFS_LSN</b> structure, call <a href="kernel.clfslsncontainer">ClfsLsnContainer</a>, <a href="kernel.clfslsnblockoffset">ClfsLsnBlockOffset</a>, and <a href="kernel.clfslsnrecordsequence">ClfsLsnRecordSequence</a>.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h)</dt>
</dl>
</td>
</tr>
</table>
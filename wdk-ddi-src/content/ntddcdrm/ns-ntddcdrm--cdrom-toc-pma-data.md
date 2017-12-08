---
UID: NS.ntddcdrm._CDROM_TOC_PMA_DATA
title: CDROM_TOC_PMA_DATA
author: windows-driver-content
description: Device control IRPs with a control code of IOCTL_CDROM_READ_TOC_EX and a format of CDROM_READ_TOC_EX_FORMAT_PMA return their output data in this structure optionally followed by a series of descriptors of type CDROM_TOC_FULL_TOC_DATA_BLOCK.
old-location: storage\cdrom_toc_pma_data.htm
old-project: storage
ms.assetid: eded7fcf-8a0a-4ad2-8ce0-e10e670344a4
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: CDROM_TOC_PMA_DATA, CDROM_TOC_PMA_DATA, *PCDROM_TOC_PMA_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CDROM_TOC_PMA_DATA
req.alt-loc: ntddcdrm.h
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

# CDROM_TOC_PMA_DATA structure



## -description
<p>Device control IRPs with a control code of <a href="..\ntddcdrm\ni-ntddcdrm-ioctl-cdrom-read-toc-ex.md">IOCTL_CDROM_READ_TOC_EX</a> and a format of CDROM_READ_TOC_EX_FORMAT_PMA return their output data in this structure optionally followed by a series of descriptors of type CDROM_TOC_FULL_TOC_DATA_BLOCK. </p>


## -syntax

````
typedef struct _CDROM_TOC_PMA_DATA {
  UCHAR                         Length[2];
  UCHAR                         Reserved1;
  UCHAR                         Reserved2;
  CDROM_TOC_FULL_TOC_DATA_BLOCK Descriptors[];
} CDROM_TOC_PMA_DATA, *PCDROM_TOC_PMA_DATA;
````


## -struct-fields
<dl>

### -field Length

<dd>
<p>Indicates the length, in bytes, of the table of contents data. This length value does not include the length of the <b>Length </b>member itself. </p>
</dd>

### -field Reserved1

<dd>
<p>Reserved.</p>
</dd>

### -field Reserved2

<dd>
<p>Reserved.</p>
</dd>

### -field Descriptors

<dd>
<p>Contains zero or more track descriptors. See <a href="..\ntddcdrm\ns-ntddcdrm--cdrom-toc-full-toc-data-block.md">CDROM_TOC_FULL_TOC_DATA_BLOCK</a> for a description of the track descriptor. </p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddcdrm.h (include Ntddcdrm.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddcdrm\ni-ntddcdrm-ioctl-cdrom-read-toc-ex.md">IOCTL_CDROM_READ_TOC_EX</a>
</dt>
<dt>
<a href="..\ntddcdrm\ns-ntddcdrm--cdrom-read-toc-ex.md">CDROM_READ_TOC_EX</a>
</dt>
<dt>
<a href="..\ntddcdrm\ns-ntddcdrm--cdrom-toc-full-toc-data-block.md">CDROM_TOC_FULL_TOC_DATA_BLOCK</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CDROM_TOC_PMA_DATA structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
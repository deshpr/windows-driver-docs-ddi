---
UID: NS.ntddcdrm._SUB_Q_MEDIA_CATALOG_NUMBER
title: SUB_Q_MEDIA_CATALOG_NUMBER
author: windows-driver-content
description: The SUB_Q_MEDIA_CATALOG_NUMBER structure contains position information and is used in conjunction with the SUB_Q_CHANNEL_DATA structure.
old-location: storage\sub_q_media_catalog_number.htm
old-project: storage
ms.assetid: 14b0aed7-1602-41a3-bc55-59da40650860
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: SUB_Q_MEDIA_CATALOG_NUMBER, SUB_Q_MEDIA_CATALOG_NUMBER, *PSUB_Q_MEDIA_CATALOG_NUMBER
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
req.alt-api: SUB_Q_MEDIA_CATALOG_NUMBER
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

# SUB_Q_MEDIA_CATALOG_NUMBER structure



## -description
<p>The SUB_Q_MEDIA_CATALOG_NUMBER structure contains position information and is used in conjunction with the <a href="..\ntddcdrm\ns-ntddcdrm--sub-q-channel-data.md">SUB_Q_CHANNEL_DATA</a> structure. </p>


## -syntax

````
typedef struct _SUB_Q_MEDIA_CATALOG_NUMBER {
  SUB_Q_HEADER Header;
  UCHAR        FormatCode;
  UCHAR        Reserved[3];
  UCHAR        Reserved1  :7;
  UCHAR        Mcval  :1;
  UCHAR        MediaCatalog[15];
} SUB_Q_MEDIA_CATALOG_NUMBER, *PSUB_Q_MEDIA_CATALOG_NUMBER;
````


## -struct-fields
<dl>

### -field Header

<dd>
<p>Indicates, among other things, the length of the Q subchannel data that was retrieved. See <a href="..\ntddcdrm\ns-ntddcdrm--sub-q-header.md">SUB_Q_HEADER</a> for further details. </p>
</dd>

### -field FormatCode

<dd>
<p>Should have a value of IOCTL_CDROM_MEDIA_CATALOG. </p>
</dd>

### -field Reserved

<dd>
<p>Reserved.</p>
</dd>

### -field Reserved1

<dd>
<p>Reserved.</p>
</dd>

### -field Mcval

<dd>
<p>Indicates that the media catalog number (MCN) data is valid if set to 1; set to zero otherwise.</p>
</dd>

### -field MediaCatalog

<dd>
<p>Contains the catalog number if <b>Mcval</b> is set to 1. </p>
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
<a href="..\ntddcdrm\ni-ntddcdrm-ioctl-cdrom-read-q-channel.md">IOCTL_CDROM_READ_Q_CHANNEL</a>
</dt>
<dt>
<a href="..\ntddcdrm\ns-ntddcdrm--cdrom-sub-q-data-format.md">CDROM_SUB_Q_DATA_FORMAT</a>
</dt>
<dt>
<a href="..\ntddcdrm\ns-ntddcdrm--sub-q-channel-data.md">SUB_Q_CHANNEL_DATA</a>
</dt>
<dt>
<a href="..\ntddcdrm\ns-ntddcdrm--sub-q-header.md">SUB_Q_HEADER</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SUB_Q_MEDIA_CATALOG_NUMBER structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
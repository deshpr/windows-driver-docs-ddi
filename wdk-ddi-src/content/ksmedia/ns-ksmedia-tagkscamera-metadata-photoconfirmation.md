---
UID: NS.ksmedia.tagKSCAMERA_METADATA_PHOTOCONFIRMATION
title: tagKSCAMERA_METADATA_PHOTOCONFIRMATION
author: windows-driver-content
description: This structure contains the photo confirmation metadata information that is filled by the camera driver.
old-location: stream\kscamera_metadata_photoconfirmation.htm
old-project: stream
ms.assetid: FA3365DC-B604-468E-AACD-AC006D2B4EAF
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: tagKSCAMERA_METADATA_PHOTOCONFIRMATION, KSCAMERA_METADATA_PHOTOCONFIRMATION, *PKSCAMERA_METADATA_PHOTOCONFIRMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSCAMERA_METADATA_PHOTOCONFIRMATION
req.alt-loc: Ksmedia.h
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

# tagKSCAMERA_METADATA_PHOTOCONFIRMATION structure



## -description
<p>This structure contains the photo confirmation metadata information that is filled by the camera driver.</p>


## -syntax

````
typedef struct tagKSCAMERA_METADATA_PHOTOCONFIRMATION {
  KSCAMERA_METADATA_ITEMHEADER Header;
  ULONG                        PhotoConfirmationIndex;
  ULONG                        Reserved;
} KSCAMERA_METADATA_PHOTOCONFIRMATION, *PKSCAMERA_METADATA_PHOTOCONFIRMATION;
````


## -struct-fields
<dl>

### -field Header

<dd>
<p>Contains the header information for the metadata item</p>
</dd>

### -field PhotoConfirmationIndex

<dd>
<p>Stores the index of the still confirmation frame. For single photo capture, this is always 0. For multishot, this corresponds to the index of the photo frame captured.</p>
</dd>

### -field Reserved

<dd>
<p>Reserved for future use.</p>
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
<dt>Ksmedia.h</dt>
</dl>
</td>
</tr>
</table>
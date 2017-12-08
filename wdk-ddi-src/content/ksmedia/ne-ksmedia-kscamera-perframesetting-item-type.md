---
UID: NE.ksmedia.KSCAMERA_PERFRAMESETTING_ITEM_TYPE
title: KSCAMERA_PERFRAMESETTING_ITEM_TYPE
author: windows-driver-content
description: This enumeration contains the different item types for the per-frame settings DDI.
old-location: stream\kscamera_perframesetting_item_type.htm
old-project: stream
ms.assetid: B4312084-E545-45FD-BA93-3BE551CE52DF
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: PKSIDEFAULTCLOCK, KSIDEFAULTCLOCK, *PKSIDEFAULTCLOCK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSCAMERA_PERFRAMESETTING_ITEM_TYPE
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

# KSCAMERA_PERFRAMESETTING_ITEM_TYPE enumeration



## -description
<p>This enumeration contains the different item types for the per-frame settings DDI.</p>


## -syntax

````
typedef enum  { 
  KSCAMERA_PERFRAMESETTING_ITEM_EXPOSURE_TIME          = 1,
  KSCAMERA_PERFRAMESETTING_ITEM_FLASH,
  KSCAMERA_PERFRAMESETTING_ITEM_EXPOSURE_COMPENSATION,
  KSCAMERA_PERFRAMESETTING_ITEM_ISO,
  KSCAMERA_PERFRAMESETTING_ITEM_FOCUS,
  KSCAMERA_PERFRAMESETTING_ITEM_PHOTOCONFIRMATION,
  KSCAMERA_PERFRAMESETTING_ITEM_CUSTOM
} KSCAMERA_PERFRAMESETTING_ITEM_TYPE;
````


## -enum-fields
<dl>

### -field KSCAMERA_PERFRAMESETTING_ITEM_EXPOSURE_TIME

<dd>
<p>This is an exposure item type.</p>
</dd>

### -field KSCAMERA_PERFRAMESETTING_ITEM_FLASH

<dd>
<p>This is a flash item type.</p>
</dd>

### -field KSCAMERA_PERFRAMESETTING_ITEM_EXPOSURE_COMPENSATION

<dd>
<p>This is an exposure compensation type.</p>
</dd>

### -field KSCAMERA_PERFRAMESETTING_ITEM_ISO

<dd>
<p>This is an ISO item type.</p>
</dd>

### -field KSCAMERA_PERFRAMESETTING_ITEM_FOCUS

<dd>
<p>This is a focus item type.</p>
</dd>

### -field KSCAMERA_PERFRAMESETTING_ITEM_PHOTOCONFIRMATION

<dd>
<p>This is a photo confirmation item type.</p>
</dd>

### -field KSCAMERA_PERFRAMESETTING_ITEM_CUSTOM

<dd>
<p>This is a custom item type.</p>
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
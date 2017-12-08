---
UID: NS.strmini._STREAM_PROPERTY_DESCRIPTOR
title: STREAM_PROPERTY_DESCRIPTOR
author: windows-driver-content
description: STREAM_PROPERTY_DESCRIPTOR specifies the parameters of property get/set requests that the class driver passes to the minidriver.
old-location: stream\stream_property_descriptor.htm
old-project: stream
ms.assetid: b72265b7-dce3-4688-bee7-2a6f7d7731f9
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: STREAM_PROPERTY_DESCRIPTOR, STREAM_PROPERTY_DESCRIPTOR, *PSTREAM_PROPERTY_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: strmini.h
req.include-header: Strmini.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STREAM_PROPERTY_DESCRIPTOR
req.alt-loc: strmini.h
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
req.product: Windows 10 or later.
---

# STREAM_PROPERTY_DESCRIPTOR structure



## -description
<p>STREAM_PROPERTY_DESCRIPTOR specifies the parameters of property get/set requests that the class driver passes to the minidriver.</p>


## -syntax

````
typedef struct _STREAM_PROPERTY_DESCRIPTOR {
  PKSPROPERTY Property;
  ULONG       PropertySetID;
  PVOID       PropertyInfo;
  ULONG       PropertyInputSize;
  ULONG       PropertyOutputSize;
} STREAM_PROPERTY_DESCRIPTOR, *PSTREAM_PROPERTY_DESCRIPTOR;
````


## -struct-fields
<dl>

### -field Property

<dd>
<p>Specifies the property to be read/written.</p>
</dd>

### -field PropertySetID

<dd>
<p>Specifies the index of the property set within either the <a href="..\strmini\ns-strmini--hw-stream-header.md">HW_STREAM_HEADER</a>'s <b>DevicePropertiesArray</b> (for minidriver properties) or the <a href="..\strmini\ns-strmini--hw-stream-information.md">HW_STREAM_INFORMATION</a>'s <b>StreamPropertiesArray</b> (for stream properties).</p>
</dd>

### -field PropertyInfo

<dd>
<p>Points to a buffer that the property data will be read from or written to.</p>
</dd>

### -field PropertyInputSize

<dd>
<p>Size of the <b>Property</b> buffer.</p>
</dd>

### -field PropertyOutputSize

<dd>
<p>Size of the <b>PropertyInfo</b> buffer.</p>
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
<dt>Strmini.h (include Strmini.h)</dt>
</dl>
</td>
</tr>
</table>
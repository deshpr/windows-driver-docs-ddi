---
UID: NS.D3DUMDDI._DXVADDI_VALUERANGE
title: _DXVADDI_VALUERANGE
author: windows-driver-content
description: The DXVADDI_VALUERANGE structure describes values of a property (such as, the value spread and default value).
old-location: display\dxvaddi_valuerange.htm
old-project: display
ms.assetid: c3013da9-8db4-4346-9be8-77b2c6de3f59
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DXVADDI_VALUERANGE, DXVADDI_VALUERANGE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVADDI_VALUERANGE
req.alt-loc: d3dumddi.h
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
---

# _DXVADDI_VALUERANGE structure



## -description
The DXVADDI_VALUERANGE structure describes values of a property (such as, the value spread and default value).


## -syntax

````
typedef struct _DXVADDI_VALUERANGE {
  DXVADDI_FIXED32 MinValue;
  DXVADDI_FIXED32 MaxValue;
  DXVADDI_FIXED32 DefaultValue;
  DXVADDI_FIXED32 StepSize;
} DXVADDI_VALUERANGE;
````


## -struct-fields

### -field MinValue

[in] A <a href="display.dxvaddi_fixed32">DXVADDI_FIXED32</a> structure that specifies the minimum value that is allowed for a given property.

### -field MaxValue

[in] A <a href="display.dxvaddi_fixed32">DXVADDI_FIXED32</a> structure that specifies the maximum value that is allowed for a given property.

### -field DefaultValue

[in] A <a href="display.dxvaddi_fixed32">DXVADDI_FIXED32</a> structure that specifies the default value for a given property.

### -field StepSize

[in] A <a href="display.dxvaddi_fixed32">DXVADDI_FIXED32</a> structure that specifies the step size increment for a given property.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.d3dddiarg_getcaps">D3DDDIARG_GETCAPS</a>
</dt>
<dt>
<a href="display.d3dddicaps_type">D3DDDICAPS_TYPE</a>
</dt>
<dt>
<a href="display.dxvaddi_videodesc">DXVADDI_VIDEODESC</a>
</dt>
<dt>
<a href="display.dxvaddi_queryprocampinput">DXVADDI_QUERYPROCAMPINPUT</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVADDI_VALUERANGE structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
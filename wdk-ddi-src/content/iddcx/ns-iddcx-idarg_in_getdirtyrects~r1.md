---
UID: NS.IDDCX.IDARG_IN_GETDIRTYRECTS~R1
title: IDARG_IN_GETDIRTYRECTS
author: windows-driver-content
description: Gives information about the parts of the surface that have changed since the last present.
old-location: display\idarg_in_getdirtyrects.htm
old-project: display
ms.assetid: 78a216c7-b208-49fb-bb8e-6758b3cb13ad
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: IDARG_IN_GETDIRTYRECTS,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDARG_IN_GETDIRTYRECTS
req.alt-loc: iddcx.h
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

# IDARG_IN_GETDIRTYRECTS structure



## -description

             
         Gives information about the parts of the surface that have changed since the last present.


## -syntax

````
typedef struct IDARG_IN_GETDIRTYRECTS {
  UINT                                    DirtyRectInCount;
  _Field_size_full_(DirtyRectCount) RECT* pDirtyRects;
} IDARG_IN_GETDIRTYRECTS, *IDARG_IN_GETDIRTYRECTS;
````


## -struct-fields

### -field DirtyRectInCount


                     [in] Number of dirty rects in the <b>pDirtyRects</b> array
                 

### -field pDirtyRects


                     [out] Pointer to the buffer where the OS can copy the dirty rects that indicate which parts of the surface have been changed since the last present.
                 

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Iddcx.h</dt>
</dl>
</td>
</tr>
</table>
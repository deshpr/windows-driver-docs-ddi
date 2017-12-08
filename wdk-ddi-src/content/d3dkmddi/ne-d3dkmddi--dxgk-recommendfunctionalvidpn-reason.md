---
UID: NE.d3dkmddi._DXGK_RECOMMENDFUNCTIONALVIDPN_REASON
title: DXGK_RECOMMENDFUNCTIONALVIDPN_REASON
author: windows-driver-content
description: The DXGK_RECOMMENDFUNCTIONALVIDPN_REASON enumeration indicates the reason for calling the display miniport driver's DxgkDdiRecommendFunctionalVidPn function.
old-location: display\dxgk_recommendfunctionalvidpn_reason.htm
old-project: display
ms.assetid: 75dda423-8d5a-4b11-a187-d6703601a366
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_RECOMMENDFUNCTIONALVIDPN_REASON
req.alt-loc: d3dkmddi.h
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
---

# DXGK_RECOMMENDFUNCTIONALVIDPN_REASON enumeration



## -description
<p>The DXGK_RECOMMENDFUNCTIONALVIDPN_REASON enumeration indicates the reason for calling the display miniport driver's <a href="display.dxgkddirecommendfunctionalvidpn">DxgkDdiRecommendFunctionalVidPn</a> function.</p>


## -syntax

````
typedef enum _DXGK_RECOMMENDFUNCTIONALVIDPN_REASON { 
  DXGK_RFVR_UNINITIALIZED  = 0,
  DXGK_RFVR_HOTKEY         = 1,
  DXGK_RFVR_USERMODE       = 2,
  DXGK_RFVR_FIRMWARE       = 3
} DXGK_RECOMMENDFUNCTIONALVIDPN_REASON;
````


## -enum-fields
<dl>

### -field DXGK_RFVR_UNINITIALIZED

<dd>
<p>Indicates that a variable of type DXGK_RECOMMENDFUNCTIONALVIDPN_REASON has not yet been assigned a meaningful value.</p>
</dd>

### -field DXGK_RFVR_HOTKEY

<dd>
<p>Indicates that the VidPN manager is calling <i>DxgkDdiRecommendFunctionalVidPn</i> because the user pressed a hot key to request a change in the way the desktop is displayed on a collection of monitors (or other display devices).</p>
</dd>

### -field DXGK_RFVR_USERMODE

<dd>
<p>Indicates that a user-mode application initiated a call to <i>DxgkDdiRecommendFunctionalVidPn</i>.</p>
</dd>

### -field DXGK_RFVR_FIRMWARE

<dd>
<p>Value indicating that the OS is requesting the driver to describe a functional VidPn which reflects the display topology and timings which are currently set, as inherited from firmware during boot or resume from hibernation.</p>
</dd>
</dl>

## -remarks
<p>The <b>RequestReason</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi--dxgkarg-recommendfunctionalvidpn.md">DXGKARG_RECOMMENDFUNCTIONALVIDPN</a> structure is a DXGK_RECOMMENDFUNCTIONALVIDPN_REASON value.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.dxgkddirecommendfunctionalvidpn">DxgkDdiRecommendFunctionalVidPn</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_RECOMMENDFUNCTIONALVIDPN_REASON enumeration%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
---
UID: NS.iddcx.IDDCX_TARGET_MODE
title: IDDCX_TARGET_MODE
author: windows-driver-content
description: Gives information about the target mode signal, including the bandwidth needed for the mode.
old-location: display\iddcx_target_mode.htm
old-project: display
ms.assetid: 10bb23fa-ff1e-4bda-ba64-59a19da5f87e
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: IDDCX_TARGET_MODE,
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
req.alt-api: IDDCX_TARGET_MODE
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
req.irql: _Must_inspect_result_
req.iface: 
---

# IDDCX_TARGET_MODE structure



## -description
<p>
                 Gives information about the target mode signal, including the bandwidth needed for the mode.
             </p>


## -syntax

````
typedef struct IDDCX_TARGET_MODE {
  UINT                      Size;
  DISPLAYCONFIG_TARGET_MODE TargetVideoSignalInfo;
  UINT64                    RequiredBandwidth;
} IDDCX_TARGET_MODE, *IDDCX_TARGET_MODE;
````


## -struct-fields
<dl>

### -field Size

<dd>
<p>
                     Total size of the structure.
                 </p>
</dd>

### -field TargetVideoSignalInfo

<dd>
<p>The details of the target mode signal. 
                 </p>
</dd>

### -field RequiredBandwidth

<dd>
<p>The display pipeline bandwidth required for this mode.
                 </p>
</dd>
</dl>

## -remarks
<p>The <a href="display.displayconfig_video_signal_info">DISPLAYCONFIG_VIDEO_SIGNAL_INFO</a> value <b>vSyncFreq</b> is the Vsync rate between the Indirect Display device and the connected monitor.  <b>vSyncFreqDivider</b> is used to calculate the rate at which the OS will update the desktop image.</p>

<p>The desktop update rate will be calculated by the formula: <a href="display.displayconfig_video_signal_info">DISPLAYCONFIG_VIDEO_SIGNAL_INFO</a> value <b>vSyncFreq</b>  divided by the <b>DISPLAYCONFIG_VIDEO_SIGNAL_INFO</b> value <b>vSyncFreqDivider</b>. </p>

<p>The <a href="display.displayconfig_video_signal_info">DISPLAYCONFIG_VIDEO_SIGNAL_INFO</a>  value <b>vSyncFreqDivider</b> cannot be zero</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Iddcx.h</dt>
</dl>
</td>
</tr>
</table>
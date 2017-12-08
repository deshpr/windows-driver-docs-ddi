---
UID: NF.stiusd.IStiDeviceControl.GetMyDeviceOpenMode
title: IStiDeviceControl::GetMyDeviceOpenMode
author: windows-driver-content
description: The IStiDeviceControl::GetMyDeviceOpenMode method allows a still image minidriver to obtain the transfer mode that an application specified when it created an instance of a still image device.
old-location: image\istidevicecontrol_getmydeviceopenmode.htm
old-project: image
ms.assetid: 814e739f-6147-4287-876e-db6fc41c5aa1
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IStiDeviceControl, GetMyDeviceOpenMode, IStiDeviceControl::GetMyDeviceOpenMode
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: stiusd.h
req.include-header: Stiusd.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IStiDeviceControl.GetMyDeviceOpenMode
req.alt-loc: stiusd.h
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
req.iface: IStiDeviceControl
req.product: Windows 10 or later.
---

# IStiDeviceControl::GetMyDeviceOpenMode method



## -description
<p>The <b>IStiDeviceControl::GetMyDeviceOpenMode</b> method allows a still image minidriver to obtain the transfer mode that an application specified when it created an instance of a still image device.</p>


## -syntax

````
HRESULT GetMyDeviceOpenMode(
   LPDWORD pdwOpenMode
);
````


## -parameters
<dl>

### -param pdwOpenMode 

<dd>
<p>Receives the mode flag that an application previously specified as the <i>dwMode</i> argument to <a href="image.istillimage_createdevice">IStillImage::CreateDevice</a>.</p>
</dd>
</dl>

## -returns
<p>If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.</p>

## -remarks
<p>A still image minidriver receives an <b>IStiDeviceControl</b> interface pointer as an input argument to its <a href="image.istiusd_initialize">IStiUSD::Initialize</a> method.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Stiusd.h (include Stiusd.h)</dt>
</dl>
</td>
</tr>
</table>
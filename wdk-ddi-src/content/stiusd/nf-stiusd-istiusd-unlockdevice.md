---
UID: NF.stiusd.IStiUSD.UnLockDevice
title: IStiUSD::UnLockDevice
author: windows-driver-content
description: A still image minidriver's IStiUSD::UnLockDevice method unlocks a device that was locked by a previous call to IStiUSD::LockDevice.
old-location: image\istiusd_unlockdevice.htm
old-project: image
ms.assetid: ae19ae38-3bca-42c8-8713-68bb161104b8
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IStiUSD, UnLockDevice, IStiUSD::UnLockDevice
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
req.alt-api: IStiUSD.UnLockDevice
req.alt-loc: Stiusd.h
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
req.iface: IStiUSD
req.product: Windows 10 or later.
---

# IStiUSD::UnLockDevice method



## -description
<p>A still image minidriver's <b>IStiUSD::UnLockDevice</b> method unlocks a device that was locked by a previous call to <a href="image.istiusd_lockdevice">IStiUSD::LockDevice</a>.</p>


## -syntax

````
STDMETHODIMP UnLockDevice();
````


## -parameters


## -returns
<p>If the operation succeeds, the method should return S_OK. Otherwise, it should return one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.</p>

<p>If the operation succeeds, the method should return S_OK. Otherwise, it should return one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.</p>

<p>If the operation succeeds, the method should return S_OK. Otherwise, it should return one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.</p>

## -remarks
<p>If a driver's <a href="image.istiusd_lockdevice">IStiUSD::LockDevice</a> method called <a href="fs.createfile">CreateFile</a>, then <b>IStiUSD::UnlockDevice</b> should call <b>CloseHandle</b>.</p>

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

## -see-also
<dl>
<dt>
<a href="image.istidevice_unlockdevice">IStiDevice::UnLockDevice</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IStiUSD::UnLockDevice method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
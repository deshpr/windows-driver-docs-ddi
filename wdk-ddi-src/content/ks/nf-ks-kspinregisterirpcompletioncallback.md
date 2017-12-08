---
UID: NF.ks.KsPinRegisterIrpCompletionCallback
title: KsPinRegisterIrpCompletionCallback function
author: windows-driver-content
description: The KsPinRegisterIrpCompletionCallback function registers a minidriver-defined callback routine for a specified pin.
old-location: stream\kspinregisterirpcompletioncallback.htm
old-project: stream
ms.assetid: d2872ea2-565b-47db-8054-876fd3c8fc4d
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KsPinRegisterIrpCompletionCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsPinRegisterIrpCompletionCallback
req.alt-loc: Ks.lib,Ks.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: PASSIVE_LEVEL
---

# KsPinRegisterIrpCompletionCallback function



## -description
The <b>KsPinRegisterIrpCompletionCallback</b> function registers a minidriver-defined callback routine for a specified pin. AVStream calls the minidriver-provided routine when an IRP completes a pass around the circuit and the frame that is associated with the IRP is about to be recycled or retired.


## -syntax

````
void KsPinRegisterIrpCompletionCallback(
  _In_ PKSPIN                Pin,
  _In_ PFNKSPINIRPCOMPLETION IrpCompletion
);
````


## -parameters

### -param Pin [in]

A pointer to the <a href="stream.kspin">KSPIN</a> structure for which to register a completion callback.

### -param IrpCompletion [in]

<dl>
<dd>
This parameter supplies the address of a <a href="stream.avstrminipinirpcompletion">AVStrMiniPinIrpCompletion</a> routine to be called when an IRP completes its traversal of the circuit and is about to be recycled or retired.
</dd>
</dl>

## -returns
None

## -remarks
<b>KsPinRegisterIrpCompletionCallback </b>must be called at IRQL=PASSIVE_LEVEL before the pin goes into KSSTATE_ACQUIRE. For more information about pin states, see <a href="stream.ksstate">KSSTATE</a>.

This function is frequently called from the pin creation dispatch. See <a href="stream.kspin_dispatch">KSPIN_DISPATCH</a>.

<b>KsPinRegisterIrpCompletionCallback</b> is only useful on IRP source pins, and is typically used on data source pins. For a data source pin, the callback is made once the IRP is completed back to the pin and is about to be recycled. For a data sink pin, however, the callback is not tied directly to IRP completion. AVStream still makes the callback when the IRP returns for recycling. This return does not occur until that IRP has passed through all the queues that need to use the data that it contains. For information about IRP source/sink pins versus data source/sink pins, see the <b>DataFlow</b> and <b>Communication</b> members of the <a href="stream.kspin_descriptor">KSPIN_DESCRIPTOR</a> structure.

<b>KsPinRegisterIrpCompletionCallback</b> differs significantly from <a href="stream.kspinregisterframereturncallback">KsPinRegisterFrameReturnCallback</a> in that this routine does not place the pin in any new mode; it simply registers a callback routine.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Ks.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
PASSIVE_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.kspinregisterframereturncallback">KsPinRegisterFrameReturnCallback</a>
</dt>
<dt>
<a href="stream.kspin_dispatch">KSPIN_DISPATCH</a>
</dt>
<dt>
<a href="stream.avstrminipincreate">AVStrMiniPinCreate</a>
</dt>
<dt>
<a href="stream.ksstate">KSSTATE</a>
</dt>
<dt>
<a href="stream.kspin">KSPIN</a>
</dt>
<dt>
<a href="stream.avstrminipinirpcompletion">AVStrMiniPinIrpCompletion</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsPinRegisterIrpCompletionCallback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
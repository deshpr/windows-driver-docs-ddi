---
UID: NF.ksproxy.IKsDataTypeCompletion.KsCompleteMediaType
title: IKsDataTypeCompletion::KsCompleteMediaType
author: windows-driver-content
description: The KsCompleteMediaType method completes a partially-specified media type that was first presented to the IAMStreamConfig::SetFormat method.
old-location: stream\iksdatatypecompletion_kscompletemediatype.htm
old-project: stream
ms.assetid: 0a6157cf-09ae-4640-9c54-3e9b91fd93a9
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: IKsDataTypeCompletion, KsCompleteMediaType, IKsDataTypeCompletion::KsCompleteMediaType
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IKsDataTypeCompletion.KsCompleteMediaType
req.alt-loc: ksproxy.h
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
req.iface: IKsDataTypeCompletion
---

# IKsDataTypeCompletion::KsCompleteMediaType method



## -description
<p>The <b>KsCompleteMediaType</b> method completes a partially-specified media type that was first presented to the <b>IAMStreamConfig::SetFormat</b> method.</p>


## -syntax

````
HRESULT KsCompleteMediaType(
  [in]      HANDLE        FilterHandle,
  [in]      ULONG         PinFactoryId,
  [in, out] AM_MEDIA_TYPE *AmMediaType
);
````


## -parameters
<dl>

### -param FilterHandle [in]

<dd>
<p>Handle to the underlying KS filter.</p>
</dd>

### -param PinFactoryId [in]

<dd>
<p>Identifier of the pin factory against which the media type is being completed.</p>
</dd>

### -param AmMediaType [in, out]

<dd>
<p>Pointer to a AM_MEDIA_TYPE structure that describes the format of the media samples. <b>KsCompleteMediaType</b> receives partially specified media samples, completes the specification, and returns.</p>
</dd>
</dl>

## -returns
<p>Returns NOERROR if successful and the media type was completed; otherwise, returns an error code.</p>

## -remarks
<p>The <b>KsCompleteMediaType</b> method is primarily used for video media types, in which the <b>biSizeImage</b> member of the <a href="stream.ks_bitmapinfoheader">KS_BITMAPINFOHEADER</a> structure is known only to the driver, because of the private compression formats supported. If required, the data type handler can query the underlying KS filter in order to complete the given media type. </p>

<p>When the proxy creates an instance of the data type handler for purposes of completing a media type, the proxy passes the media type to the <a href="stream.iksdatatypehandler_kssetmediatype">IKsDataTypeHandler::KsSetMediaType</a> method to first initialize this data type handler to the particular media type. </p>

<p>For more information about <b>IAMStreamConfig::SetFormat</b> and AM_MEDIA_TYPE, see the Microsoft Windows SDK documentation.</p>

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
<dt>Ksproxy.h (include Ksproxy.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.iksdatatypehandler_kssetmediatype">IKsDataTypeHandler::KsSetMediaType</a>
</dt>
<dt>
<a href="stream.ks_bitmapinfoheader">KS_BITMAPINFOHEADER</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsDataTypeCompletion::KsCompleteMediaType method%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
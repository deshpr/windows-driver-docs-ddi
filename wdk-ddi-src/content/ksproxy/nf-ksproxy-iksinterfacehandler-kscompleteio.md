---
UID: NF.ksproxy.IKsInterfaceHandler.KsCompleteIo
title: IKsInterfaceHandler::KsCompleteIo
author: windows-driver-content
description: The KsCompleteIo method cleans up extended headers and releases media samples after input and output (I/O) complete.
old-location: stream\iksinterfacehandler_kscompleteio.htm
old-project: stream
ms.assetid: 2ff69f59-5fbd-43fd-afe5-9717d7928d2a
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: IKsInterfaceHandler, KsCompleteIo, IKsInterfaceHandler::KsCompleteIo
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
req.alt-api: IKsInterfaceHandler.KsCompleteIo
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
req.iface: IKsInterfaceHandler
---

# IKsInterfaceHandler::KsCompleteIo method



## -description
<p>The <b>KsCompleteIo</b> method cleans up extended headers and releases media samples after input and output (I/O) complete. </p>


## -syntax

````
HRESULT KsCompleteIo(
  [in, out] PKSSTREAM_SEGMENT StreamSegment
);
````


## -parameters
<dl>

### -param StreamSegment [in, out]

<dd>
<p>Pointer to a <a href="..\ksproxy\ns-ksproxy--ksstream-segment.md">KSSTREAM_SEGMENT</a> structure that contains header information for a stream segment to complete. </p>
</dd>
</dl>

## -returns
<p>Returns NOERROR if successful; otherwise, returns an error code.</p>

## -remarks
<p>The <b>KsCompleteIo</b> method discards allocated memory, updates media samples, and decrements the count of wait items for the proxy. </p>

<p>The <b>KsCompleteIo</b> method must determine the type of I/O operation that the <a href="stream.iksinterfacehandler_ksprocessmediasamples">IKsInterfaceHandler::KsProcessMediaSamples</a> method completed from the <b>IoOperation</b> member of the KSSTREAM_SEGMENT structure. If the I/O operation was reading data from a stream (<b>KsIoOperation_Read</b> of the KSIOOPERATION enumerated type), <b>KsCompleteIo</b> performs the following actions to deliver the sample from an output pin to the connected input pin:</p>

<p>Reflects the stream header information in the <b>IMediaSample</b> interface. </p>

<p>Calls the <a href="stream.ikspin_ksdeliver">IKsPin::KsDeliver</a> method of the output pin to deliver the sample. <b>KsDeliver</b> releases the sample so that when queuing buffers to the device, the sample can be retrieved if it is the last sample. The input pin then completes the I/O and it is safe to release the sample. </p>

<p>For more information about <b>IMediaSample</b>, see the Microsoft Windows SDK documentation.</p>

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
<a href="stream.iksinterfacehandler_ksprocessmediasamples">IKsInterfaceHandler::KsProcessMediaSamples</a>
</dt>
<dt>
<a href="stream.ikspin_ksdeliver">IKsPin::KsDeliver</a>
</dt>
<dt>
<a href="..\ksproxy\ns-ksproxy--ksstream-segment.md">KSSTREAM_SEGMENT</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsInterfaceHandler::KsCompleteIo method%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
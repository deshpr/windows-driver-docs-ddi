---
UID: NF.wudfusb.IUsbTargetPipeContinuousReaderCallbackReadersFailed.OnReaderFailure
title: IUsbTargetPipeContinuousReaderCallbackReadersFailed::OnReaderFailure
author: windows-driver-content
description: A driver's OnReaderFailure event callback function informs the driver that a continuous reader has reported an error while processing a read request.
old-location: wdf\iusbtargetpipecontinuousreadercallbackreadersfailed_onreaderfailure.htm
old-project: wdf
ms.assetid: ad91208e-e57a-4b80-b1a1-13b9f7eb1119
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IUsbTargetPipeContinuousReaderCallbackReadersFailed, OnReaderFailure, IUsbTargetPipeContinuousReaderCallbackReadersFailed::OnReaderFailure
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wudfusb.h
req.include-header: Wudfusb.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.alt-api: IUsbTargetPipeContinuousReaderCallbackReadersFailed.OnReaderFailure
req.alt-loc: wudfusb.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.iface: IUsbTargetPipeContinuousReaderCallbackReadersFailed
req.product: Windows 10 or later.
---

# IUsbTargetPipeContinuousReaderCallbackReadersFailed::OnReaderFailure method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]</p>
<p>A driver's <b>OnReaderFailure</b> event callback function informs the driver that a continuous reader has reported an error while processing a read request.</p>


## -syntax

````
BOOL OnReaderFailure(
  [in] IWDFUsbTargetPipe *pPipe,
  [in] HRESULT           hrStatus
);
````


## -parameters
<dl>

### -param pPipe [in]

<dd>
<p>A pointer to the <a href="..\wudfusb\nn-wudfusb-iwdfusbtargetpipe.md">IWDFUsbTargetPipe</a> interface for the USB pipe on which the driver has enabled a continuous reader.</p>
</dd>

### -param hrStatus [in]

<dd>
<p>The HRESULT-typed status value that the USB pipe's I/O target returned.</p>
</dd>
</dl>

## -returns
<p>The <b>OnReaderFailure</b> event callback function must return a Boolean value. If the return value is <b>TRUE</b>, the framework resets the USB pipe and then restarts the continuous reader. If the callback function returns <b>FALSE</b>, the framework does not reset the device or restart the continuous reader.</p>

## -remarks
<p>To register an <b>OnReaderFailure</b> callback function, your driver must provide a pointer to the driver's <a href="..\wudfusb\nn-wudfusb-iusbtargetpipecontinuousreadercallbackreadersfailed.md">IUsbTargetPipeContinuousReaderCallbackReadersFailed</a> interface when it calls <a href="wdf.iwdfusbtargetpipe2_configurecontinuousreader">IWDFUsbTargetPipe2::ConfigureContinuousReader</a>.</p>

<p>If a driver has created a continuous reader for a USB pipe, the framework calls the driver's <b>OnReaderFailure</b> callback function if the driver's I/O target reports an error when it completes a read request. (If the I/O target successfully completes the request, the framework calls the driver's <a href="wdf.iusbtargetpipecontinuousreadercallbackreadcomplete_onreadercompletion">IUsbTargetPipeContinuousReaderCallbackReadComplete::OnReaderCompletion</a> callback function.) </p>

<p>Before the framework calls a driver's <b>OnReaderFailure</b> callback function, it tries to cancel all in-progress read requests. No read requests are in progress when the framework calls the <b>OnReaderFailure</b> callback function. The framework does not queue any additional read requests until the <b>OnReaderFailure</b> callback function returns.</p>

<p>For information about how the framework synchronizes calls to the <b>OnReaderFailure</b> callback function with calls to other callback functions, see the Remarks section of <a href="wdf.iusbtargetpipecontinuousreadercallbackreadcomplete_onreadercompletion">IUsbTargetPipeContinuousReaderCallbackReadComplete::OnReaderCompletion</a>.</p>

<p>The <b>OnReaderFailure</b> callback function must not call <a href="wdf.iwdfiotargetstatemanagement_stop">IWDFIoTargetStateManagement::Stop</a> to stop the continuous reader's USB target. (In fact, calling <b>IWDFIoTargetStateManagement::Stop</b> in an <b>OnReaderFailure</b> callback function causes a deadlock.) In addition, the callback function must not call <a href="wdf.iwdfiotargetstatemanagement_start">IWDFIoTargetStateManagement::Start</a> to restart the continuous reader. Instead, the framework restarts the reader if the callback function returns <b>TRUE</b>. For more information about when to call <b>IWDFIoTargetStateManagement::Start</b> and <b>IWDFIoTargetStateManagement::Stop</b> for a continuous reader, see <a href="wdf.working_with_usb_pipes_in_umdf">Working with USB Pipes in UMDF</a>.</p>

<p>If a driver does not provide an <b>OnReaderFailure</b> callback function and the driver's I/O target reports an error, the framework resets the USB pipe and restarts the continuous reader. </p>

<p>For more information about the <b>OnReaderFailure</b> callback function and USB I/O targets, see <a href="wdf.usb_i_o_targets_in_umdf">Handling a USB I/O Target</a>.</p>

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
<p>End of support</p>
</th>
<td width="70%">
<p>Unavailable in UMDF 2.0 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>1.9</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wudfusb.h (include Wudfusb.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wudfusb\nn-wudfusb-iusbtargetpipecontinuousreadercallbackreadersfailed.md">IUsbTargetPipeContinuousReaderCallbackReadersFailed</a>
</dt>
<dt>
<a href="wdf.iusbtargetpipecontinuousreadercallbackreadcomplete_onreadercompletion">IUsbTargetPipeContinuousReaderCallbackReadComplete::OnReaderCompletion</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IUsbTargetPipeContinuousReaderCallbackReadersFailed::OnReaderFailure method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
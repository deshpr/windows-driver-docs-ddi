---
UID: NC.wdfusb.EVT_WDF_USB_READER_COMPLETION_ROUTINE
title: EVT_WDF_USB_READER_COMPLETION_ROUTINE
author: windows-driver-content
description: A driver's EvtUsbTargetPipeReadComplete event callback function informs the driver that a continuous reader has successfully completed a read request.
old-location: wdf\evtusbtargetpipereadcomplete.htm
old-project: wdf
ms.assetid: da762d78-6d73-4ab9-83a8-297c6f48855b
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WDF_TIMER_CONFIG, WDF_TIMER_CONFIG, *PWDF_TIMER_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfusb.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: EvtUsbTargetPipeReadComplete
req.alt-loc: WdfUsb.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL  (See Remarks section.)
req.iface: 
req.product: Windows 10 or later.
---

# EVT_WDF_USB_READER_COMPLETION_ROUTINE callback



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]</p>
<p>A driver's <i>EvtUsbTargetPipeReadComplete</i> event callback function informs the driver that a continuous reader has successfully completed a read request.</p>


## -prototype

````
EVT_WDF_USB_READER_COMPLETION_ROUTINE EvtUsbTargetPipeReadComplete;

VOID EvtUsbTargetPipeReadComplete(
  _In_ WDFUSBPIPE Pipe,
  _In_ WDFMEMORY  Buffer,
  _In_ size_t     NumBytesTransferred,
  _In_ WDFCONTEXT Context
)
{ ... }
````


## -parameters
<dl>

### -param Pipe [in]

<dd>
<p>A handle to a framework pipe object.</p>
</dd>

### -param Buffer [in]

<dd>
<p>A handle to a framework memory object that represents a buffer that contains data from the device.</p>
</dd>

### -param NumBytesTransferred [in]

<dd>
<p>The number of bytes of data that are in the read buffer.</p>
</dd>

### -param Context [in]

<dd>
<p>Driver-defined context information that the driver specified in the <b>EvtUsbTargetPipeReadCompleteContext</b> member of the pipe's <a href="..\wdfusb\ns-wdfusb--wdf-usb-continuous-reader-config.md">WDF_USB_CONTINUOUS_READER_CONFIG</a> structure. </p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>To register an <i>EvtUsbTargetPipeReadComplete</i> callback function, the driver must place the function's address in a <a href="..\wdfusb\ns-wdfusb--wdf-usb-continuous-reader-config.md">WDF_USB_CONTINUOUS_READER_CONFIG</a> structure.</p>

<p>If a driver has created a continuous reader for a USB pipe, the framework calls the driver's <i>EvtUsbTargetPipeReadComplete</i> callback function each time the driver's I/O target successfully completes a read request. The callback function is called at the IRQL at which the I/O target completed the read request, which is typically IRQL = DISPATCH_LEVEL, but no higher than DISPATCH_LEVEL. (If the I/O target does not successfully complete a request, the framework calls the driver's <a href="..\wdfusb\nc-wdfusb-evt-wdf-usb-readers-failed.md">EvtUsbTargetPipeReadersFailed</a> callback function.) </p>

<p>To access the buffer that contains data that was read from the device, the driver can call <a href="..\wdfmemory\nf-wdfmemory-wdfmemorygetbuffer.md">WdfMemoryGetBuffer</a>. The framework writes the data into the buffer, after the header that is defined by the <b>HeaderLength</b> member of the <a href="..\wdfusb\ns-wdfusb--wdf-usb-continuous-reader-config.md">WDF_USB_CONTINUOUS_READER_CONFIG</a> structure. Note that the pointer that <b>WdfMemoryGetBuffer</b> returns points to the beginning of the header, but the <i>EvtUsbTargetPipeReadComplete</i> callback function's <i>NumBytesTransferred</i> parameter does <i>not</i> include the header's length.</p>

<p>By default, the framework deletes the buffer's memory object after the <i>EvtUsbTargetPipeReadComplete</i> callback function returns. However, you might want the memory object to remain valid after the callback function returns. For example, you might want your driver to store the object handle in the framework pipe object's context space so that the driver can process the memory object's contents after the callback function returns. To extend the lifetime of the memory object, the callback function must pass the memory object's handle to <a href="https://msdn.microsoft.com/library/windows/hardware/ff548758">WdfObjectReference</a>. Subsequently, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548739">WdfObjectDereference</a> so that the framework can delete the object.</p>

<p>The framework synchronizes calls to the <i>EvtUsbTargetPipeReadComplete</i> and <a href="..\wdfusb\nc-wdfusb-evt-wdf-usb-readers-failed.md">EvtUsbTargetPipeReadersFailed</a> callback functions according to the following rules:</p>

<p>These callback functions do not run simultaneously for an individual USB pipe.</p>

<p>If the driver creates multiple continuous readers for multiple USB pipes, with multiple <i>EvtUsbTargetPipeReadComplete</i> and <a href="..\wdfusb\nc-wdfusb-evt-wdf-usb-readers-failed.md">EvtUsbTargetPipeReadersFailed</a> callback functions, the multiple callback functions can run simultaneously.</p>

<p>If the driver has specified the default <a href="..\wdfusb\ns-wdfusb--wdf-usb-continuous-reader-config.md">NumPendingReads</a> value or a value that is greater than 1, and if a read request completes while the <i>EvtUsbTargetPipeReadComplete</i> callback function is executing, the framework can call the <i>EvtUsbTargetPipeReadComplete</i> callback function again before the callback function returns.</p>

<p>The framework does not synchronize these callback functions with any other callback functions.</p>

<p>In the <b>BufferAttributes</b> member of the <a href="..\wdfusb\ns-wdfusb--wdf-usb-continuous-reader-config.md">WDF_USB_CONTINUOUS_READER_CONFIG</a> structure, your driver can specify <a href="..\wdfobject\nc-wdfobject-evt-wdf-object-context-cleanup.md">EvtCleanupCallback</a> and <a href="..\wdfobject\nc-wdfobject-evt-wdf-object-context-destroy.md">EvtDestroyCallback</a> callback functions for the memory object. If you specify an <i>EvtCleanupCallback</i> callback function, the framework will call that callback function when it attempts to delete the memory object, after the <i>EvtUsbTargetPipeReadComplete</i> callback function returns. If the <i>EvtUsbTargetPipeReadComplete</i> callback function has called <a href="https://msdn.microsoft.com/library/windows/hardware/ff548758">WdfObjectReference</a>, the <i>EvtCleanupCallback</i> callback function (if provided) must not call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548739">WdfObjectDereference</a>.</p>

<p>The driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548739">WdfObjectDereference</a> when it has finished using the memory object. The framework can then call the driver's <a href="..\wdfobject\nc-wdfobject-evt-wdf-object-context-destroy.md">EvtDestroyCallback</a> callback function (if provided) and delete the memory object.</p>

<p>For more information about the <i>EvtUsbTargetPipeReadComplete</i> callback function and USB I/O targets, see <a href="wdf.usb_i_o_targets">USB I/O Targets</a>.</p>

<p>To define an <i>EvtUsbTargetPipeReadComplete</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define an <i>EvtUsbTargetPipeReadComplete</i> callback function that is named <i>MyUsbTargetPipeReadComplete</i>, use the <b>EVT_WDF_USB_READER_COMPLETION_ROUTINE</b> type as shown in this code example:</p>

<p>To define an <i>EvtUsbTargetPipeReadComplete</i> callback function that is named <b>MyUsbTargetPipeReadComplete</b>, you must first provide a function declaration that SDV and other verification tools require, as follows:</p>

<p>Then, implement your callback function as follows:</p>

<p>The <b>EVT_WDF_USB_READER_COMPLETION_ROUTINE</b> function type is defined in the WdfUsb.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_USB_READER_COMPLETION_ROUTINE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum KMDF version</p>
</th>
<td width="70%">
<p>1.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>2.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>WdfUsb.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;=DISPATCH_LEVEL  (See Remarks section.)</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfusb\nc-wdfusb-evt-wdf-usb-readers-failed.md">EvtUsbTargetPipeReadersFailed</a>
</dt>
<dt>
<a href="..\wdfusb\ns-wdfusb--wdf-usb-continuous-reader-config.md">WDF_USB_CONTINUOUS_READER_CONFIG</a>
</dt>
<dt>
<a href="..\wdfmemory\nf-wdfmemory-wdfmemorygetbuffer.md">WdfMemoryGetBuffer</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_USB_READER_COMPLETION_ROUTINE callback function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
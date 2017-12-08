---
UID: NC.wdfio.EVT_WDF_IO_QUEUE_IO_READ
title: EVT_WDF_IO_QUEUE_IO_READ
author: windows-driver-content
description: A driver's EvtIoRead event callback function processes a specified read request.
old-location: wdf\evtioread.htm
old-project: wdf
ms.assetid: d6fbb153-1355-4e94-b5d3-a218bd8c565d
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WDF_INTERRUPT_INFO, WDF_INTERRUPT_INFO, *PWDF_INTERRUPT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: EvtIoRead
req.alt-loc: Wdfio.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL (see Remarks section)
req.iface: 
req.product: Windows 10 or later.
---

# EVT_WDF_IO_QUEUE_IO_READ callback



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]</p>
<p>A driver's <i>EvtIoRead</i> event callback function processes a specified read request.</p>


## -prototype

````
EVT_WDF_IO_QUEUE_IO_READ EvtIoRead;

VOID EvtIoRead(
  _In_ WDFQUEUE   Queue,
  _In_ WDFREQUEST Request,
  _In_ size_t     Length
)
{ ... }
````


## -parameters
<dl>

### -param Queue [in]

<dd>
<p>A handle to the framework queue object that is associated with the I/O request.</p>
</dd>

### -param Request [in]

<dd>
<p>A handle to a framework request object.</p>
</dd>

### -param Length [in]

<dd>
<p>The number of bytes to be read.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>A driver registers an <i>EvtIoRead</i> callback function when it calls <a href="..\wdfio\nf-wdfio-wdfioqueuecreate.md">WdfIoQueueCreate</a>. For more information about calling <b>WdfIoQueueCreate</b>, see  <a href="wdf.creating_i_o_queues">Creating I/O Queues</a>.</p>

<p>If a driver has registered an <i>EvtIoRead</i> callback function for a device's I/O queue, the callback function receives every read request from the queue. For more information, see <a href="wdf.request_handlers">Request Handlers</a>.</p>

<p>The <i>EvtIoRead</i> callback function must process each received I/O request in some manner. For more information, see <a href="wdf.processing_i_o_requests">Processing I/O Requests</a>.</p>

<p>Read requests require an output buffer, which receives data that the driver provides. For information about how the driver can access a read request's buffer, see <a href="wdf.accessing_data_buffers_in_kmdf_drivers">Accessing Data Buffers in Framework-Based Drivers</a>.</p>

<p>This callback function can be called at IRQL &lt;= DISPATCH_LEVEL, unless the <b>ExecutionLevel</b> member of the device or driver's <a href="..\wdfobject\ns-wdfobject--wdf-object-attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure is set to <b>WdfExecutionLevelPassive</b>.</p>

<p>If the IRQL is PASSIVE_LEVEL, the framework calls the callback function within a <a href="https://msdn.microsoft.com/3781498a-45e9-4f24-8fd2-830eed61298c">critical region</a>.</p>

<p>For more information about IRQL levels for request handlers, see <a href="wdf.using_automatic_synchronization">Using Automatic Synchronization</a>.</p>

<p>A driver's <i>EvtIoRead</i> callback function should not call the following queue object methods:<dl>
<dd>
<a href="..\wdfio\nf-wdfio-wdfioqueuedrainsynchronously.md">WdfIoQueueDrainSynchronously</a>
</dd>
<dd>
<a href="..\wdfio\nf-wdfio-wdfioqueuepurgesynchronously.md">WdfIoQueuePurgeSynchronously</a>
</dd>
<dd>
<a href="..\wdfio\nf-wdfio-wdfioqueuestopsynchronously.md">WdfIoQueueStopSynchronously</a>
</dd>
</dl>
</p>

<p>To define an <i>EvtIoRead</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define an <i>EvtIoRead</i> callback function that is named <i>MyIoRead</i>, use the <b>EVT_WDF_IO_QUEUE_IO_READ</b> type as shown in this code example:</p>

<p>Then, implement your callback function as follows:</p>

<p>The <b>EVT_WDF_IO_QUEUE_IO_READ</b> function type is defined in the Wdfio.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_IO_QUEUE_IO_READ</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.</p>

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
<dt>Wdfio.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= DISPATCH_LEVEL (see Remarks section)</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfio\nf-wdfio-wdfioqueuecreate.md">WdfIoQueueCreate</a>
</dt>
<dt>
<a href="..\wdfobject\ns-wdfobject--wdf-object-attributes.md">WDF_OBJECT_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\wdfio\nc-wdfio-evt-wdf-io-queue-io-default.md">EvtIoDefault</a>
</dt>
<dt>
<a href="..\wdfio\nc-wdfio-evt-wdf-io-queue-io-write.md">EvtIoWrite</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_IO_QUEUE_IO_READ callback function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
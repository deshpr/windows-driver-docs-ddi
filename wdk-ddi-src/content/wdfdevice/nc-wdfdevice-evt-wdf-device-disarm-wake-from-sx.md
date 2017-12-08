---
UID: NC.wdfdevice.EVT_WDF_DEVICE_DISARM_WAKE_FROM_SX
title: EVT_WDF_DEVICE_DISARM_WAKE_FROM_SX
author: windows-driver-content
description: A driver's EvtDeviceDisarmWakeFromSx event callback function disarms (that is, disables) a device's ability to trigger a wake signal while the device and system are in low-power states.
old-location: wdf\evtdevicedisarmwakefromsx.htm
old-project: wdf
ms.assetid: 79bf7a42-5053-428a-a78b-dd8bdff93a69
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WDF_REL_TIMEOUT_IN_US
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: EvtDeviceDisarmWakeFromSx
req.alt-loc: Wdfdevice.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.iface: 
req.product: Windows 10 or later.
---

# EVT_WDF_DEVICE_DISARM_WAKE_FROM_SX callback



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]</p>
<p>A driver's <i>EvtDeviceDisarmWakeFromSx</i> event callback function disarms (that is, disables) a device's ability to trigger a wake signal while the device and system are in low-power states.</p>


## -prototype

````
EVT_WDF_DEVICE_DISARM_WAKE_FROM_SX EvtDeviceDisarmWakeFromSx;

VOID EvtDeviceDisarmWakeFromSx(
  _In_ WDFDEVICE Device
)
{ ... }
````


## -parameters
<dl>

### -param Device [in]

<dd>
<p>A handle to a framework device object.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>To register an <i>EvtDeviceDisarmWakeFromSx</i> callback function, a driver must call  <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpowerpolicyeventcallbacks.md">WdfDeviceInitSetPowerPolicyEventCallbacks</a>.</p>

<p>If the driver has registered this callback function, the framework calls it after the framework has determined that system power is being restored, and after the bus driver completes the <a href="https://msdn.microsoft.com/ed582644-af51-4841-be59-6a3deb6d9de5">wait/wake IRP</a>. Before calling the driver's <i>EvtDeviceDisarmWakeFromSx</i> callback function, the framework calls the driver's <a href="..\wdfdevice\nc-wdfdevice-evt-wdf-device-d0-entry.md">EvtDeviceD0Entry</a>, <a href="..\wdfinterrupt\nc-wdfinterrupt-evt-wdf-interrupt-enable.md">EvtInterruptEnable</a>, and <a href="..\wdfdevice\nc-wdfdevice-evt-wdf-device-wake-from-sx-triggered.md">EvtDeviceWakeFromSxTriggered</a> callback functions.</p>

<p>The <i>EvtDeviceDisarmWakeFromSx</i> callback function must perform any hardware operations that are needed to disable the device's ability to trigger a wake signal after the power has been lowered.</p>

<p>For more information about when the framework calls this callback function, see <a href="wdf.pnp_and_power_management_scenarios">PnP and Power Management Scenarios</a>.</p>

<p>For more information about this callback function, see <a href="wdf.supporting_system_wake_up">Supporting System Wake-Up</a>.</p>

<p>The <i>EvtDeviceDisarmWakeFromSx</i> callback function is called at IRQL = PASSIVE_LEVEL. You should not make this callback function <a href="wdf.creating_pageable_code_in_a_kmdf_driver">pageable</a>.</p>

<p>To define an <i>EvtDeviceDisarmWakeFromSx</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define an <i>EvtDeviceDisarmWakeFromSx</i> callback function that is named <i>MyDeviceDisarmWakeFromSx</i>, use the <b>EVT_WDF_DEVICE_DISARM_WAKE_FROM_SX</b> type as shown in this code example:</p>

<p>Then, implement your callback function as follows:</p>

<p>The <b>EVT_WDF_DEVICE_DISARM_WAKE_FROM_SX</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_DISARM_WAKE_FROM_SX</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.</p>

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
<dt>Wdfdevice.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL (see Remarks section)</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfdevice\nc-wdfdevice-evt-wdf-device-arm-wake-from-sx.md">EvtDeviceArmWakeFromSx</a>
</dt>
<dt>
<a href="..\wdfdevice\nc-wdfdevice-evt-wdf-device-disarm-wake-from-s0.md">EvtDeviceDisarmWakeFromS0</a>
</dt>
<dt>
<a href="..\wdfdevice\nc-wdfdevice-evt-wdf-device-wake-from-sx-triggered.md">EvtDeviceWakeFromSxTriggered</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DEVICE_DISARM_WAKE_FROM_SX callback function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
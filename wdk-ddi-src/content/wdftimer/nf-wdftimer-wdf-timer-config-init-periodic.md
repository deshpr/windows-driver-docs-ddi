---
UID: NF.wdftimer.WDF_TIMER_CONFIG_INIT_PERIODIC
title: WDF_TIMER_CONFIG_INIT_PERIODIC
author: windows-driver-content
description: The WDF_TIMER_CONFIG_INIT_PERIODIC function initializes a WDF_TIMER_CONFIG structure for a periodic timer.
old-location: wdf\wdf_timer_config_init_periodic.htm
old-project: wdf
ms.assetid: 44a5b4dd-c654-4af1-afd6-6e59d2cd1ff8
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WDF_TIMER_CONFIG_INIT_PERIODIC
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdftimer.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WDF_TIMER_CONFIG_INIT_PERIODIC
req.alt-loc: None,None.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: None
req.dll: 
req.irql: Any level
req.iface: 
req.product: Windows 10 or later.
---

# WDF_TIMER_CONFIG_INIT_PERIODIC function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]</p>
<p>The <b>WDF_TIMER_CONFIG_INIT_PERIODIC</b> function initializes a <a href="..\wdftimer\ns-wdftimer--wdf-timer-config.md">WDF_TIMER_CONFIG</a> structure for a periodic timer.</p>


## -syntax

````
VOID WDF_TIMER_CONFIG_INIT_PERIODIC(
  _In_ PWDF_TIMER_CONFIG Config,
  _In_ PFN_WDF_TIMER     EvtTimerFunc,
  _In_ LONG              Period
);
````


## -parameters
<dl>

### -param Config [in]

<dd>
<p>A pointer to a <a href="..\wdftimer\ns-wdftimer--wdf-timer-config.md">WDF_TIMER_CONFIG</a> structure.</p>
</dd>

### -param EvtTimerFunc [in]

<dd>
<p>A pointer to a driver-supplied <a href="wdf.evttimerfunc">EvtTimerFunc</a> callback function.</p>
</dd>

### -param Period [in]

<dd>
<p>A time value. For more information about specifying this value, see <a href="..\wdftimer\ns-wdftimer--wdf-timer-config.md">WDF_TIMER_CONFIG</a>.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>The <b>WDF_TIMER_CONFIG_INIT_PERIODIC</b> function zeros the specified <a href="..\wdftimer\ns-wdftimer--wdf-timer-config.md">WDF_TIMER_CONFIG</a> structure. Then it sets the structure's <b>Size</b> member, stores the <i>EvtTimerFunc</i> pointer and <i>Period</i> value, sets the <b>TolerableDelay</b> member to zero and sets the <b>AutomaticSerialization</b> member to <b>TRUE</b>. </p>

<p>The following code example initializes a <a href="..\wdftimer\ns-wdftimer--wdf-timer-config.md">WDF_TIMER_CONFIG</a> structure and a <a href="..\wdfobject\ns-wdfobject--wdf-object-attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure and then calls <a href="..\wdftimer\nf-wdftimer-wdftimercreate.md">WdfTimerCreate</a>.</p>

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
<dt>Wdftimer.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>None</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>Any level</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.evttimerfunc">EvtTimerFunc</a>
</dt>
<dt>
<a href="..\wdftimer\ns-wdftimer--wdf-timer-config.md">WDF_TIMER_CONFIG</a>
</dt>
<dt>
<a href="..\wdftimer\nf-wdftimer-wdf-timer-config-init.md">WDF_TIMER_CONFIG_INIT</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_TIMER_CONFIG_INIT_PERIODIC function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
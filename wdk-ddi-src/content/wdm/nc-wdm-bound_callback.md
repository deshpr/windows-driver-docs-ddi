---
UID: NC.wdm.BOUND_CALLBACK
title: BOUND_CALLBACK
author: windows-driver-content
description: The BoundCallback routine is executed whenever the system issues a bounds exception for a user-mode thread.
old-location: kernel\boundcallback.htm
old-project: kernel
ms.assetid: D9047BB2-2FCD-41DE-B1E1-DE89AAA40ED7
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _WDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME, PWDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BoundCallback
req.alt-loc: Wdm.h
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
req.product: Windows 10 or later.
---

# BOUND_CALLBACK callback



## -description
The <i>BoundCallback</i> routine is executed whenever the system issues a bounds exception for a user-mode thread.



## -prototype

````
BOUND_CALLBACK BoundCallback;

BOUND_CALLBACK_STATUS BoundCallback(void)
{ ... }
````


## -parameters


## -returns
A <a href="kernel.bound_callback_status">BOUND_CALLBACK_STATUS</a> value that indicates how the bounds exception was processed by the callback function. 

A <a href="kernel.bound_callback_status">BOUND_CALLBACK_STATUS</a> value that indicates how the bounds exception was processed by the callback function. 

A <a href="kernel.bound_callback_status">BOUND_CALLBACK_STATUS</a> value that indicates how the bounds exception was processed by the callback function. 


## -remarks
Drivers can supply a <i>BoundCallback</i> that is called when the system issues a bounds exception.

Use <a href="kernel.keregisterboundcallback">KeRegisterBoundCallback</a> to register a <i>BoundCallback</i> routine. A driver can subsequently remove the callback by using the <a href="kernel.kederegisterboundcallback">KeDeregisterBoundCallback</a> routine. If the driver can be unloaded, it must remove any registered callbacks in its <a href="kernel.unload">Unload</a> routine.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 10.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.keregisterboundcallback">KeRegisterBoundCallback</a>
</dt>
<dt>
<a href="kernel.kederegisterboundcallback">KeDeregisterBoundCallback</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20BOUND_CALLBACK routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

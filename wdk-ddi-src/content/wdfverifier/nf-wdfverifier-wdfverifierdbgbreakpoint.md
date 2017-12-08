---
UID: NF.wdfverifier.WdfVerifierDbgBreakPoint
title: WdfVerifierDbgBreakPoint function
author: windows-driver-content
description: The WdfVerifierDbgBreakPoint function breaks into a kernel debugger, if a debugger is running.
old-location: wdf\wdfverifierdbgbreakpoint.htm
old-project: wdf
ms.assetid: 55b8a6de-f20b-4d2d-8235-4837bc4a0d7d
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WdfVerifierDbgBreakPoint
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfverifier.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfVerifierDbgBreakPoint
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: Any level
req.product: Windows 10 or later.
---

# WdfVerifierDbgBreakPoint function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]
The <b>WdfVerifierDbgBreakPoint</b> function breaks into a kernel debugger, if a debugger is running.


## -syntax

````
VOID WdfVerifierDbgBreakPoint(void);
````


## -parameters


## -returns
None

None

None

## -remarks
The <b>WdfVerifierDbgBreakPoint</b> function breaks into a kernel debugger if one of the following is true:

For more information about registry entries that you can use to debug your driver, see <a href="wdf.registry_values_for_debugging_kmdf_drivers">Registry Entries for Debugging Framework-Based Drivers</a>.

For more information about debugging your driver, see <a href="wdf.debugging_a_kmdf_driver">Debugging a KMDF Driver</a>.

The following code example shows how a driver might handle a failure to obtain an I/O request's output buffer.

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
Minimum KMDF version
</th>
<td width="70%">
1.0
</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version
</th>
<td width="70%">
2.0
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdfverifier.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (KMDF); </dt>
<dt>WUDFx02000.dll (UMDF)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
Any level
</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules
</th>
<td width="70%">
<a href="devtest.kmdf_drivercreate">DriverCreate</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdfverifierkebugcheck">WdfVerifierKeBugCheck</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfVerifierDbgBreakPoint function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
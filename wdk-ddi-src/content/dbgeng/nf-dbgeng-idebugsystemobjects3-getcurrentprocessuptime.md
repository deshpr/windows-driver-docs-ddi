---
UID: NF.dbgeng.IDebugSystemObjects3.GetCurrentProcessUpTime
title: IDebugSystemObjects3::GetCurrentProcessUpTime
author: windows-driver-content
description: The GetCurrentProcessUpTime method returns the length of time the current process has been running.
old-location: debugger\getcurrentprocessuptime.htm
old-project: debugger
ms.assetid: 6c6f3824-5e04-45df-8128-f3778aaa3636
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugSystemObjects3, GetCurrentProcessUpTime, IDebugSystemObjects3::GetCurrentProcessUpTime
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugSystemObjects2.GetCurrentProcessUpTime,IDebugSystemObjects3.GetCurrentProcessUpTime,IDebugSystemObjects4.GetCurrentProcessUpTime
req.alt-loc: dbgeng.h
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
req.iface: IDebugSystemObjects3
---

# IDebugSystemObjects3::GetCurrentProcessUpTime method



## -description
<p>The <b>GetCurrentProcessUpTime</b> method returns the length of time the current process has been running.</p>


## -syntax

````
HRESULT GetCurrentProcessUpTime(
  [out] PULONG UpTime
);
````


## -parameters
<dl>

### -param UpTime [out]

<dd>
<p>Receives the number of seconds the current process has been running.</p>
</dd>
</dl>

## -returns
<p>This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p>

<p> </p>

## -remarks


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
<dt>Dbgeng.h (include Dbgeng.h)</dt>
</dl>
</td>
</tr>
</table>
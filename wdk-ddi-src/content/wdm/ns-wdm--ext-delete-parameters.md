---
UID: NS.wdm._EXT_DELETE_PARAMETERS
title: EXT_DELETE_PARAMETERS
author: windows-driver-content
description: The EXT_DELETE_PARAMETERS structure contains an extended set of parameters for the ExDeleteTimer routine.
old-location: kernel\ext_delete_parameters.htm
old-project: kernel
ms.assetid: B2EADC0E-837A-4231-8794-43933DAA69E7
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: EXT_DELETE_PARAMETERS, EXT_DELETE_PARAMETERS, *PEXT_DELETE_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.1.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: EXT_DELETE_PARAMETERS
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
req.irql: PASSIVE_LEVEL (see Remarks section)
req.iface: 
req.product: Windows 10 or later.
---

# EXT_DELETE_PARAMETERS structure



## -description
<p>The <b>EXT_DELETE_PARAMETERS</b> structure contains an extended set of parameters for the <a href="..\wdm\nf-wdm-exdeletetimer.md">ExDeleteTimer</a> routine.</p>


## -syntax

````
typedef struct _EXT_DELETE_PARAMETERS {
  ULONG                Version;
  ULONG                Reserved;
  PEXT_DELETE_CALLBACK DeleteCallback;
  PVOID                DeleteContext;
} EXT_DELETE_PARAMETERS, *PEXT_DELETE_PARAMETERS;
````


## -struct-fields
<dl>

### -field Version

<dd>
<p>The version number of this <b>EXT_DELETE_PARAMETERS</b> structure. The <a href="..\wdm\nf-wdm-exinitializedeletetimerparameters.md">ExInitializeDeleteTimerParameters</a> routine sets this member to the correct version number.</p>
</dd>

### -field Reserved

<dd>
<p>Set to zero. The <b>ExInitializeDeleteTimerParameters</b> routine sets this member to zero.</p>
</dd>

### -field DeleteCallback

<dd>
<p>A pointer to a driver-implemented <a href="kernel.extimerdeletecallback">ExTimerDeleteCallback</a> callback routine. The operating system calls this routine when the timer is deleted. This parameter is optional and can be <b>NULL</b> if no timer-deletion callback routine is needed.

The <b>ExInitializeDeleteTimerParameters</b> routine sets this member to <b>NULL</b>. For more information, see Remarks.</p>
</dd>

### -field DeleteContext

<dd>
<p>A context value for the timer-deletion callback routine. The operating system passes this value as a parameter to the timer-deletion callback routine, if one is specified. This parameter is typically a pointer to a caller-defined structure that contains context information used by the callback routine. This parameter is optional and can be set to <b>NULL</b> if no context information is needed. 

The <b>ExInitializeDeleteTimerParameters</b> routine sets this member to <b>NULL</b>.</p>
</dd>
</dl>

## -remarks
<p>The <i>Parameters</i> parameter of the <a href="..\wdm\nf-wdm-exdeletetimer.md">ExDeleteTimer</a> routine is a pointer to an <b>EXT_DELETE_PARAMETERS</b> structure. Before passing an <b>EXT_DELETE_PARAMETERS</b> structure to this routine, call the <a href="..\wdm\nf-wdm-exinitializedeletetimerparameters.md">ExInitializeDeleteTimerParameters</a> routine to initialize the structure.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported starting with Windows 8.1.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-exdeletetimer.md">ExDeleteTimer</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-exinitializedeletetimerparameters.md">ExInitializeDeleteTimerParameters</a>
</dt>
<dt>
<a href="kernel.extimerdeletecallback">ExTimerDeleteCallback</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20EXT_DELETE_PARAMETERS structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
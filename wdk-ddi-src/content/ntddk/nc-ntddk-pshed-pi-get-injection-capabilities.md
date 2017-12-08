---
UID: NC.ntddk.PSHED_PI_GET_INJECTION_CAPABILITIES
title: PSHED_PI_GET_INJECTION_CAPABILITIES
author: windows-driver-content
description: A PSHED plug-in's GetInjectionCapabilities callback function returns an error injection capabilities union that describes the types of hardware errors that can be injected into the hardware platform.
old-location: whea\getinjectioncapabilities.htm
old-project: whea
ms.assetid: 8cb19677-11b8-4594-b4dd-ebd00fae07d4
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: FILTER_INITIALIZATION_DATA, FILTER_INITIALIZATION_DATA, *PFILTER_INITIALIZATION_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GetInjectionCapabilities
req.alt-loc: Ntddk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.iface: 
---

# PSHED_PI_GET_INJECTION_CAPABILITIES callback



## -description
<p>A PSHED plug-in's <i>GetInjectionCapabilities</i> callback function returns an error injection capabilities union that describes the types of hardware errors that can be injected into the hardware platform.</p>


## -prototype

````
PSHED_PI_GET_INJECTION_CAPABILITIES GetInjectionCapabilities;

NTSTATUS GetInjectionCapabilities(
  _Inout_opt_ PVOID                              PluginContext,
  _Out_       PWHEA_ERROR_INJECTION_CAPABILITIES Capabilities
)
{ ... }
````


## -parameters
<dl>

### -param PluginContext [in, out, optional]

<dd>
<p>A pointer to the context area that was specified in the <b>Context</b> member of the <a href="..\ntddk\ns-ntddk--whea-pshed-plugin-registration-packet.md">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure when the PSHED plug-in called the <a href="..\ntddk\nf-ntddk-pshedregisterplugin.md">PshedRegisterPlugin</a> function to register itself with the PSHED.</p>
</dd>

### -param Capabilities [out]

<dd>
<p>A pointer to a <a href="..\ntddk\ns-ntddk--whea-error-injection-capabilities.md">WHEA_ERROR_INJECTION_CAPABILITIES</a> union. This union receives the data that describes the types of hardware errors that can be injected into the hardware platform.</p>
</dd>
</dl>

## -returns
<p>A PSHED plug-in's <i>GetInjectionCapabilities</i> callback function returns one of the following NTSTATUS codes:</p><dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><p>The data that describes the types of hardware errors that can be injected into the hardware platform was successfully returned in the WHEA_ERROR_INJECTION_CAPABILITIES union pointed to by the <i>Capabilities</i> parameter.</p><dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl><p>An error occurred.</p>

<p> </p>

## -remarks
<p>A PSHED plug-in that participates in error injection sets the <b>Callbacks.GetInjectionCapabilities </b>and <b>Callbacks.InjectError </b>members of the <a href="..\ntddk\ns-ntddk--whea-pshed-plugin-registration-packet.md">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure to point to its <i>GetInjectionCapabilities</i> and <a href="..\ntddk\nc-ntddk-pshed-pi-inject-error.md">InjectError</a> callback functions when the plug-in calls the <a href="..\ntddk\nf-ntddk-pshedregisterplugin.md">PshedRegisterPlugin</a> function to register itself with the PSHED. The PSHED plug-in must also set the <b>PshedFAErrorInjection</b> flag in the <b>FunctionalAreaMask</b> member of the WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure.</p>

<p>The Windows kernel calls into the PSHED to retrieve information about the types of hardware errors that can be injected into the hardware platform in response to an error injection capabilities inquiry by a WHEA management application. If a PSHED plug-in is registered to participate in error injection, the PSHED calls the PSHED plug-in's <i>GetInjectionCapabilities</i> callback function to retrieve information about additional types of hardware errors that can be injected into the hardware platform.</p>

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
<p>Version</p>
</th>
<td width="70%">
<p>Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;=DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddk\nf-ntddk-pshedregisterplugin.md">PshedRegisterPlugin</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-pshed-pi-inject-error.md">InjectError</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk--whea-error-injection-capabilities.md">WHEA_ERROR_INJECTION_CAPABILITIES</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk--whea-pshed-plugin-registration-packet.md">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20PSHED_PI_GET_INJECTION_CAPABILITIES callback function%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
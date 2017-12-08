---
UID: NC.ndkpi.NDK_FN_CONTROL_CQ_INTERRUPT_MODERATION
title: NDK_FN_CONTROL_CQ_INTERRUPT_MODERATION
author: windows-driver-content
description: The NdkControlCqInterruptModeration (NDK_FN_CONTROL_CQ_INTERRUPT_MODERATION) function controls interrupt moderation on an NDK completion queue (CQ).
old-location: netvista\ndk_fn_control_cq_interrupt_moderation.htm
old-project: netvista
ms.assetid: 44EB6C92-1ADA-4675-9E19-BAB79097FF5B
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: NDIS_WWAN_VISIBLE_PROVIDERS, NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdkControlCqInterruptModeration
req.alt-loc: ndkpi.h
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

# NDK_FN_CONTROL_CQ_INTERRUPT_MODERATION callback



## -description
<p>The <i>NdkControlCqInterruptModeration</i> (<i>NDK_FN_CONTROL_CQ_INTERRUPT_MODERATION</i>) function controls interrupt moderation on an NDK completion queue (CQ).</p>
<p>For more information about interrupt moderation, see <a href="netvista.interrupt_moderation">Interrupt Moderation</a>.</p>


## -prototype

````
NDK_FN_CONTROL_CQ_INTERRUPT_MODERATION NdkControlCqInterruptModeration;

NTSTATUS NdkControlCqInterruptModeration(
  _In_ NDK_CQ *pNdkCq,
  _In_ ULONG  ModerationInterval,
  _In_ ULONG  ModerationCount
)
{ ... }
````


## -parameters
<dl>

### -param pNdkCq [in]

<dd>
<p>A pointer to an NDK completion queue object (<a href="..\ndkpi\ns-ndkpi--ndk-cq.md">NDK_CQ</a>).
</p>
</dd>

### -param ModerationInterval [in]

<dd>
<p>
The maximum number of microseconds that a provider can defer interrupting the host CPU after a completion placed into the CQ satisfies an arm request. If <i>ModerationInterval</i> is zero, the provider performs no interrupt moderation  on the CQ regardless of the value of the <i>ModerationCount</i> parameter. If <i>ModerationInterval</i> is MAXULONG, the  <i>ModerationCount</i> controls the interrupt moderation on the CQ. If <i>ModerationInterval</i> is larger than the maximum moderation interval that the adapter supports or if the adapter’s timer granularity is larger, the provider can round down the interval value. 
</p>
</dd>

### -param ModerationCount [in]

<dd>
<p>
The maximum number of completions that a provider can accumulate in the CQ before interrupting the host CPU to satisfy a CQ arm request. If  <i>ModerationInterval</i> is zero  or one,  the provider performs no interrupt moderation on the CQ regardless of the value of the <i>ModerationInterval</i> parameter. If <i>ModerationCount</i> is MAXULONG or larger than the depth of the CQ,   <i>ModerationInterval</i> controls the interrupt moderation on the CQ. 
</p>
</dd>
</dl>

## -returns
<p>The 
     <i>NDK_FN_CONTROL_CQ_INTERRUPT_MODERATION</i> function returns one of the following NTSTATUS codes.</p><dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><p>The operation completed successfully.</p><dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl><p> The request failed due to insufficient resources. </p><dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl><p>The NDK 
provider does not support CQ interrupt moderation control with <a href="..\ndkpi\nc-ndkpi-ndk-fn-control-cq-interrupt-moderation.md">NDK_FN_CONTROL_CQ_INTERRUPT_MODERATION</a>. A provider that sets the NDK_ADAPTER_FLAG_CQ_INTERRUPT_MODERATION_SUPPORT flag in the <a href="netvista.ndk_adapter_info">NDK_ADAPTER_INFO</a> structure's <b>AdapterFlags</b> member must not return this status code.
</p><dl>
<dt><b>STATUS_INVALID_PARAMETER_MIX</b></dt>
</dl><p>The NDK 
consumer provided a MAXULONG for <i>ModerationInterval</i> and MAXULONG or a value larger than the  number of completion entries that the CQ can hold for <i>ModerationCount</i> at the same time.
</p><dl>
<dt><b>Other status codes</b></dt>
</dl><p>An error occurred. </p>

<p> </p>

## -remarks
<p>NDK consumers must not call <i>NDK_FN_CONTROL_CQ_INTERRUPT_MODERATION</i> unless the provider sets the NDK_ADAPTER_FLAG_CQ_INTERRUPT_MODERATION_SUPPORTED  flag in the <a href="netvista.ndk_adapter_info">NDK_ADAPTER_INFO</a> structure's <b>AdapterFlags</b> member. For a provider that sets the NDK_ADAPTER_FLAG_CQ_INTERRUPT_MODERATION_SUPPORTED flag, the NDK consumer can call this function at any point after a CQ is created. The default behavior for a CQ is no interrupt moderation. The NDK consumer must not call this function on the same CQ concurrently.
</p>

<p>The NDK consumer must not specify a MAXULONG for <i>ModerationInterval</i> and MAXULONG or a value larger than the  number of completion entries that the CQ can hold  (<i>CqDepth</i>) for <i>ModerationCount</i> at the same time. Otherwise, the provider will return STATUS_INVALID_PARAMETER_MIX.
</p>

<p>The NDK consumer can call <i>NDK_FN_CONTROL_CQ_INTERRUPT_MODERATION</i> multiple times. A provider might not apply the settings before returning from this function.  However, the provider must not delay the application of the settings indefinitely. If the consumer issues another call to this function while the provider has not yet applied the settings from a previous invocation of the function, the provider must make the most recently provided settings effective as soon as possible. That is, either the provider must cancel the application of the previous settings and apply the new settings, or wait for the application of previous settings to complete and apply the new settings.</p>

<p>Providers that indicate support for interrupt moderation with the NDK_ADAPTER_FLAG_CQ_INTERRUPT_MODERATION_SUPPORTED flag must normally handle <i>NDK_FN_CONTROL_CQ_INTERRUPT_MODERATION</i> successfully and return STATUS_SUCCESS.  However,  a provider can fail the request due to a resource shortage such as a memory allocation failure. In this case,  the provider must return STATUS_INSUFFICIENT_RESOURCES. Providers cannot return STATUS_PENDING from this function. Providers that do not indicate support for this function with the NDK_ADAPTER_FLAG_CQ_INTERRUPT_MODERATION_SUPPORTED flag must still implement this function. In this case,  this function  must return STATUS_NOT_SUPPORTED.
</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>None supported</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.30 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndkpi.h (include Ndkpi.h)</dt>
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
<a href="netvista.ndk_adapter_info">NDK_ADAPTER_INFO</a>
</dt>
<dt>
<a href="..\ndkpi\ns-ndkpi--ndk-cq.md">NDK_CQ</a>
</dt>
<dt>
<a href="..\ndkpi\ns-ndkpi--ndk-cq-dispatch.md">NDK_CQ_DISPATCH</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_CONTROL_CQ_INTERRUPT_MODERATION callback function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
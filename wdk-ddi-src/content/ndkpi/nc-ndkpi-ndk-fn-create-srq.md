---
UID: NC.ndkpi.NDK_FN_CREATE_SRQ
title: NDK_FN_CREATE_SRQ
author: windows-driver-content
description: The NdkCreateSrq (NDK_FN_CREATE_SRQ) function creates an NDK shared receive queue (SRQ) object.
old-location: netvista\ndk_fn_create_srq.htm
old-project: netvista
ms.assetid: 83125C65-021F-4EEE-8819-B73752908DE7
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
req.alt-api: NdkCreateSrq
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

# NDK_FN_CREATE_SRQ callback



## -description
<p>The <i>NdkCreateSrq</i> (<i>NDK_FN_CREATE_SRQ</i>) function creates an NDK shared receive queue (SRQ) object.</p>


## -prototype

````
NDK_FN_CREATE_SRQ NdkCreateSrq;

NTSTATUS NdkCreateSrq(
  _In_     NDK_PD                           *pNdkPd,
  _In_     ULONG                            SrqDepth,
  _In_     ULONG                            MaxReceiveRequestSge,
  _In_     ULONG                            NotifyThreshold,
  _In_opt_ NDK_FN_SRQ_NOTIFICATION_CALLBACK SrqNotification,
  _In_opt_ PVOID                            SrqNotificationContext,
  _In_opt_ GROUP_AFFINITY                   *Affinity,
  _In_     NDK_FN_CREATE_COMPLETION         CreateCompletion,
  _In_opt_ PVOID                            RequestContext,
           _Outptr_ NDK_SRQ                 **ppNdkSrq
)
{ ... }
````


## -parameters
<dl>

### -param pNdkPd [in]

<dd>
<p>A pointer to an NDK protection domain (PD) object (<a href="..\ndkpi\ns-ndkpi--ndk-pd.md">NDK_PD</a>).</p>
</dd>

### -param SrqDepth [in]

<dd>
<p>The maximum number of receive requests that can be outstanding over the SRQ. This value  must be less than or equal to the value in the <b>MaxSrqDepth</b> member that is specified in the <a href="netvista.ndk_adapter_info">NDK_ADAPTER_INFO</a> structure.</p>
</dd>

### -param MaxReceiveRequestSge [in]

<dd>
<p>The maximum number of SGEs that are supported in a single receive request. This value must be less than or equal to the value in the <b>MaxReceiveRequestSge</b> member that is specified in the NDK_ADAPTER_INFO structure.</p>
</dd>

### -param NotifyThreshold [in]

<dd>
<p>The minimum number of queued receive requests for triggering SRQ notification callbacks.</p>
</dd>

### -param SrqNotification [in, optional]

<dd>
<p>An optional <i>NdkSrqNotificationCallback</i> function(<a href="..\ndkpi\nc-ndkpi-ndk-fn-srq-notification-callback.md">NDK_FN_SRQ_NOTIFICATION_CALLBACK</a>) which the provider calls if the  queued receive request count falls below the threshold that is specified in the  <i>NotifyThreshold</i> parameter.</p>
</dd>

### -param SrqNotificationContext [in, optional]

<dd>
<p>A context value that the NDK provider passes back to the <i>NdkSrqNotificationCallback</i> function that is specified in the <i>SrqNotification</i> parameter.</p>
</dd>

### -param Affinity [in, optional]

<dd>
<p>An affinity mask (<a href="..\miniport\ns-miniport--group-affinity.md">GROUP_AFFINITY</a>) that specifies preferred processors that the consumer would choose to run the <i>NdkSrqNotificationCallback</i> callbacks. Providers should honor the processor preferences if their underlying hardware allows it, but consumers cannot assume that <i>NdkSrqNotificationCallback</i> callbacks will occur only on the preferred processors. Set <i>Affinity</i> to NULL if there are no preferred processors.</p>
</dd>

### -param CreateCompletion [in]

<dd>
<p>A pointer to an <i>NdkCreateCompletion</i> (<a href="..\ndkpi\nc-ndkpi-ndk-fn-create-completion.md">NDK_FN_CREATE_COMPLETION</a>) function that completes the creation of an NDK object.</p>
</dd>

### -param RequestContext [in, optional]

<dd>
<p>A context value that the NDK provider passes back to the <i>NdkCreateCompletion</i> function that is specified in the <i>CreateCompletion</i> parameter.</p>
</dd>

### -param ppNdkSrq 

<dd>
<p>A pointer to a created SRQ object (<a href="..\ndkpi\ns-ndkpi--ndk-srq.md">NDK_SRQ</a>) is returned in this location if the request succeeds without returning STATUS_PENDING. If the request returns STATUS_PENDING then this parameter is ignored and the created object is returned with the callback that is specified in the  <i>CreateCompletion</i> parameter.</p>
</dd>
</dl>

## -returns
<p>The 
     <i>NdkCreateSrq</i> function returns one of the following NTSTATUS codes.</p><dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><p>The SRQ object was created successfully and returned with the  <i>*ppNdkSrq</i> parameter.</p><dl>
<dt><b>STATUS_PENDING</b></dt>
</dl><p> The operation is pending and will be completed later. The provider will call the function specified in the <i>CreateCompletion</i> parameter (<a href="..\ndkpi\nc-ndkpi-ndk-fn-create-completion.md">NDK_FN_CREATE_COMPLETION</a>) to complete the pending operation.
 </p><dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl><p>The request failed because the requested <i>SrqDepth</i> or <i>MaxReceiveRequestSge</i> is not within the limits that are specified in the <a href="netvista.ndk_adapter_info">NDK_ADAPTER_INFO</a> structure.</p><dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl><p>The request failed due to insufficient resources. </p><dl>
<dt><b>Other status codes</b></dt>
</dl><p>An error occurred. </p>

<p> </p>

## -remarks
<p>The <i>NdkCreateSrq</i> function creates an NDK shared receive queue (SRQ) object. If the function returns STATUS_SUCCESS, the created object is returned in the <i>ppNdkSrq</i> parameter. If <i>NdkCreateSrq</i> returns STATUS_PENDING, the created object is returned by the <i>NdkCreateCompletion</i> (<a href="..\ndkpi\nc-ndkpi-ndk-fn-create-completion.md">NDK_FN_CREATE_COMPLETION</a>) function that is specified in the <i>CreateCompletion</i> parameter.</p>

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
<a href="..\miniport\ns-miniport--group-affinity.md">GROUP_AFFINITY</a>
</dt>
<dt>
<a href="netvista.ndk_adapter_info">NDK_ADAPTER_INFO</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk-fn-create-completion.md">NDK_FN_CREATE_COMPLETION</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk-fn-srq-notification-callback.md">NDK_FN_SRQ_NOTIFICATION_CALLBACK</a>
</dt>
<dt>
<a href="..\ndkpi\ns-ndkpi--ndk-pd.md">NDK_PD</a>
</dt>
<dt>
<a href="..\ndkpi\ns-ndkpi--ndk-srq.md">NDK_SRQ</a>
</dt>
<dt>
<a href="netvista.ndkpi_object_lifetime_requirements">NDKPI Object Lifetime Requirements</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_CREATE_SRQ callback function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
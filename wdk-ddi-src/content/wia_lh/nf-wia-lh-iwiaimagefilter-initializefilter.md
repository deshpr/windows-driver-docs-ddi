---
UID: NF.wia_lh.IWiaImageFilter.InitializeFilter
title: IWiaImageFilter::InitializeFilter
author: windows-driver-content
description: The IWiaImageFilter::InitializeFilter method stores the references to pWiaItem2 and pWiaTransferCallback parameters passed into the method.
old-location: image\iwiaimagefilter_initializefilter.htm
old-project: image
ms.assetid: 03e359aa-4745-4961-a342-79f725468aab
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IWiaImageFilter, InitializeFilter, IWiaImageFilter::InitializeFilter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wia_lh.h
req.include-header: Wia_lh.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IWiaImageFilter.InitializeFilter
req.alt-loc: wia_lh.h
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
req.iface: IWiaImageFilter
req.product: Windows 10 or later.
---

# IWiaImageFilter::InitializeFilter method



## -description
<p>The <b>IWiaImageFilter::InitializeFilter</b> method stores the references to <i>pWiaItem2</i> and <i>pWiaTransferCallback</i> parameters passed into the method.</p>


## -syntax

````
HRESULT InitializeFilter(
  [in] IWiaItem2              *pWiaItem2,
  [in] IWiaTransferCallback   *pWiaTransferCallback 
);
````


## -parameters
<dl>

### -param pWiaItem2 [in]

<dd>
<p>Points to the <b>IWiaItem2</b> item that the image acquisition was initiated for by the application. In the case of <b>IWiaTransfer::Download</b>, it is the WIA item from which we obtained the <b>IWiaTransfer</b> interface, and in the case of the Preview component, it is the item that we pass into the <b>IWiaPreview::GetNewPreview</b> method.</p>
</dd>

### -param pWiaTransferCallback  [in]

<dd>
<p>Points to a <a href="image.iwiatransfercallback_interface">IWiaTransferCallback</a> interface. The IWiaTransferCallback interface is the application's callback interface, which is passed to <b>IWiaTransfer::Download</b> and <b>IWiaPreview::GetNewPreview</b>. 
</p>
</dd>
</dl>

## -returns
<p>Returns S_OK on success, or a standard COM error code on failure.

</p>

## -remarks
<p>This method is called by the COM proxy object (described in the Microsoft Windows SDK documentation) before the download call reaches the WIA service. This happens in two cases: when an application calls <b>IWiaTransfer::Download</b> method and when an application calls the <b>IWiaPreview::GetNewPreview</b> method. </p>

<p>All that <b>IWiaImageFilter::InitializeFilter</b> is required to do is to store the references to <i>pWiaItem2</i> and <i>pWiaTransferCallback</i> that are passed into it. These interface pointers should be stored as member variables in this method and <b>AddRef</b> should be called for each interface pointer. These two interface pointers are needed in the filter's implementation of <b>IWiaTransferCallback::TransferCallback</b> and <b>IWiaTransferCallback::GetNextStream</b> methods.</p>

<p>The <b>IWiaTransferCallback</b> and <b>IWiaPreview</b> interfaces are described in the Windows SDK documentation.</p>

<p>This method cannot be invoked directly by the application.</p>

<p>The <b>IWiaItem2, IWiaPreview</b> and <b>IWiaTransfer</b> interfaces are described in the Windows SDK documentation.</p>

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
<p>Available in Windows Vista and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wia_lh.h (include Wia_lh.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="image.iwiatransfercallback_interface">IWiaTransferCallback Interface</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IWiaImageFilter::InitializeFilter method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
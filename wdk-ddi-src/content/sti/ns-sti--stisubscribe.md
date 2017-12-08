---
UID: NS.sti._STISUBSCRIBE
title: STISUBSCRIBE
author: windows-driver-content
description: The STISUBSCRIBE structure is used as a parameter for the IStiDevice::Subscribe method.
old-location: image\stisubscribe.htm
old-project: image
ms.assetid: 68859180-274d-44f8-9ccf-1cae0348f902
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: STISUBSCRIBE, STISUBSCRIBE, *LPSTISUBSCRIBE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: sti.h
req.include-header: Sti.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STISUBSCRIBE
req.alt-loc: sti.h
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
req.iface: IStiDevice
req.product: Windows 10 or later.
---

# STISUBSCRIBE structure



## -description
<p>The STISUBSCRIBE structure is used as a parameter for the <a href="image.istidevice_subscribe">IStiDevice::Subscribe</a> method.</p>


## -syntax

````
typedef struct _STISUBSCRIBE {
  DWORD  dwSize;
  DWORD  dwFlags;
  DWORD  dwFilter;
  HWND   hWndNotify;
  HANDLE hEvent;
  UINT   uiNotificationMessage;
} STISUBSCRIBE, *LPSTISUBSCRIBE;
````


## -struct-fields
<dl>

### -field dwSize

<dd>
<p>Caller-supplied size, in bytes, of the STISUBSCRIBE structure.</p>
</dd>

### -field dwFlags

<dd>
<p>One of the following bit flags, defined in <i>Sti.h</i>.</p>
<p></p>
<dl>

### -field STI_SUBSCRIBE_FLAG_EVENT

<dd>
<p>Event notifications should be delivered to the application by calls to <b>SetEvent</b>. The <b>hEvent</b> member contains a Win32 event handle. </p>
<p>This bit flag is preferred for security reasons. It is available on Windows Me, Windows XP and later operating system versions.</p>
</dd>
</dl>
<p></p>
<dl>

### -field STI_SUBSCRIBE_FLAG_WINDOW

<dd>
<p>Event notifications should be delivered to the application using window messages. The <b>dwWndNotify</b> member contains a window handle and <b>uiNotificationMessage</b> contains a window message.</p>
<p>This bit flag is obsolete. It is not available on Windows XP or later operating system versions.</p>
</dd>
</dl>
</dd>

### -field dwFilter

<dd>
<p>Reserved for system use.</p>
</dd>

### -field hWndNotify

<dd>
<p>Handle to an application window that should receive the message specified by <b>uiNotificationMessage</b> when an event occurs. Used only if STI_SUBSCRIBE_FLAG_WINDOW is set in <b>dwFlags</b>.</p>
</dd>

### -field hEvent

<dd>
<p>Handle to a Win32 event created with <b>CreateEvent</b>, which the event monitor will use with <b>SetEvent</b> when an event occurs and for which the application can wait. Used only if STI_SUBSCRIBE_FLAG_WINDOW is set in <b>dwFlags</b>.</p>
</dd>

### -field uiNotificationMessage

<dd>
<p>Window message that should be passed to the <b>dwWndNotify</b> window when an event occurs.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Sti.h (include Sti.h)</dt>
</dl>
</td>
</tr>
</table>
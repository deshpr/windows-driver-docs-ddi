---
UID: NE.wwan._WWAN_UICC_PASSTHROUGH_ACTION
title: WWAN_UICC_PASSTHROUGH_ACTION
author: windows-driver-content
description: The WWAN_UICC_PASSTHROUGH_ACTION enumeration defines the passthrough action specified by the MB host for a modem miniport adapter after it resets a UICC smart card.
old-location: netvista\wwan_uicc_passthrough_action.htm
old-project: netvista
ms.assetid: 4C9293CB-D92D-4C31-929F-16C1B8918933
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WUDF_WORKITEM_CONFIG, WUDF_WORKITEM_CONFIG, *PWUDF_WORKITEM_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WWAN_UICC_PASSTHROUGH_ACTION
req.alt-loc: wwan.h
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
req.iface: 
req.product: Windows 10 or later.
---

# WWAN_UICC_PASSTHROUGH_ACTION enumeration



## -description
<p>The <b>WWAN_UICC_PASSTHROUGH_ACTION</b> enumeration defines the passthrough action specified by the MB host for a modem miniport adapter after it resets a UICC smart card.</p>


## -syntax

````
typedef enum _WWAN_UICC_PASSTHROUGH_ACTION { 
  WwanUiccPassThroughDisable        = 0,
  WwanUiccPassThroughEnable         = 1,
  WwanUiccPassThroughActionMaximum
} WWAN_UICC_PASSTHROUGH_ACTION;
````


## -enum-fields
<dl>

### -field WwanUiccPassThroughDisable

<dd>
<p>Indicates to disable passthrough to the UICC after reset. When UICC passthrough is disabled, the MB host treats the UICC as a regular Telecom UICC and expects a Telecom UICC file system to be present on the UICC.</p>
</dd>

### -field WwanUiccPassThroughEnable

<dd>
<p>Indicates to enable passthrough to the UICC after reset. When UICC passthrough is enabled, the modem miniport adapter treats the UICC as if it were in a passthrough mode that enables communication between the host and UICC, even if the UICC has no Telecom UICC file system. The miniport adapter does not send any APDUs to the card and does not interfere at any time with the communication between the host and the UICC.</p>
</dd>

### -field WwanUiccPassThroughActionMaximum

<dd>
<p>The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Windows 10, version 1709</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wwan.h (include Wwan.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wwan\ns-wwan--wwan-set-uicc-reset.md">WWAN_SET_UICC_RESET</a>
</dt>
<dt>
<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-uicc-reset-operations">MB UICC reset operations</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_UICC_PASSTHROUGH_ACTION enumeration%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
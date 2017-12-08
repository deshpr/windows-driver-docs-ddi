---
UID: NS.ksmedia.PKSPROPERTY_TUNER_MODE_S
title: PKSPROPERTY_TUNER_MODE_S
author: windows-driver-content
description: The KSPROPERTY_TUNER_MODE_S structure describes the mode of a TV or radio tuner device.
old-location: stream\ksproperty_tuner_mode_s.htm
old-project: stream
ms.assetid: a3e443e5-1766-4292-a25a-ad673734bac1
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: PKSPROPERTY_TUNER_MODE_S, KSPROPERTY_TUNER_MODE_S, *PKSPROPERTY_TUNER_MODE_S
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSPROPERTY_TUNER_MODE_S
req.alt-loc: ksmedia.h
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
---

# PKSPROPERTY_TUNER_MODE_S structure



## -description
<p>The KSPROPERTY_TUNER_MODE_S structure describes the mode of a TV or radio tuner device.</p>


## -syntax

````
typedef struct {
  KSPROPERTY Property;
  ULONG      Mode;
} KSPROPERTY_TUNER_MODE_S, *PKSPROPERTY_TUNER_MODE_S;
````


## -struct-fields
<dl>

### -field Property

<dd>
<p>Specifies an initialized <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> structure that describes the property set, property ID, and request type.</p>
</dd>

### -field Mode

<dd>
<p>Specifies the current tuner mode. If the request is a Get request, the minidriver should return the current tuner mode. If the request is a Set request, the minidriver should switch the current tuner mode to the specified value. This member can be one of the following tuner modes from the KSPROPERTY_TUNER_MODES enumeration that is defined in <i>K</i><i>smedia.h</i>:</p>
<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<p>KSPROPERTY_TUNER_MODE_TV</p>
</td>
<td>
<p>Indicates that the tuner is currently tuning (get) or should switch to tuning broadcast or cable television channels (set).</p>
</td>
</tr>
<tr>
<td>
<p>KSPROPERTY_TUNER_MODE_FM_RADIO</p>
</td>
<td>
<p>Indicates that the tuner is currently tuning (get) or should switch to tuning (set) FM radio channels.</p>
</td>
</tr>
<tr>
<td>
<p>KSPROPERTY_TUNER_MODE_AM_RADIO</p>
</td>
<td>
<p>Indicates that the tuner is currently tuning (get) or should switch to tuning (set) AM radio channels.</p>
</td>
</tr>
<tr>
<td>
<p>KSPROPERTY_TUNER_MODE_DSS</p>
</td>
<td>
<p>Indicates that the tuner is currently tuning (get) or should switch to tuning (set) tuning DSS channels.</p>
</td>
</tr>
<tr>
<td>
<p>KSPROPERTY_TUNER_MODE_ATSC</p>
</td>
<td>
<p>Indicates that the tuner is capable of tuning (get) or should switch to tuning (set) Advanced Television Systems Committee broadcasts (Digital TV for the United States). This setting can also be used by DVB-T and DVB-C systems.</p>
</td>
</tr>
</table>
<p> </p>
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
<dt>Ksmedia.h (include Ksmedia.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567800">PROPSETID_TUNER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565862">KSPROPERTY_TUNER_MODE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_TUNER_MODE_S structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
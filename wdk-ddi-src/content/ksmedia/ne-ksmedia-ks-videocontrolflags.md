---
UID: NE.ksmedia.KS_VideoControlFlags
title: KS_VideoControlFlags
author: windows-driver-content
description: The KS_VideoControlFlags enumeration defines video control capabilities for a specific stream.
old-location: stream\ks_videocontrolflags.htm
old-project: stream
ms.assetid: 7f8b3727-132c-41c8-a252-0f9c8812002f
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: PKSIDEFAULTCLOCK, KSIDEFAULTCLOCK, *PKSIDEFAULTCLOCK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KS_VideoControlFlags
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

# KS_VideoControlFlags enumeration



## -description
<p>The KS_VideoControlFlags enumeration defines video control capabilities for a specific stream.</p>


## -syntax

````
typedef enum  { 
  KS_VideoControlFlag_FlipHorizontal                  = 0x0001,
  KS_VideoControlFlag_FlipVertical                    = 0x0002,
  KS_Obsolete_VideoControlFlag_ExternalTriggerEnable  = 0x0010,
  KS_Obsolete_VideoControlFlag_Trigger                = 0x0020,
  KS_VideoControlFlag_ExternalTriggerEnable           = 0x0004,
  KS_VideoControlFlag_Trigger                         = 0x0008,
  KS_VideoControlFlag_IndependentImagePin             = 0x0040,
#if NTDDI_VERSION >= NTDDI_WIN8
  KS_VideoControlFlag_StillCapturePreviewFrame        = 0x0080,
  KS_VideoControlFlag_StartPhotoSequenceCapture       = 0x0100,
  KS_VideoControlFlag_StopPhotoSequenceCapture        = 0x0200

#endif } KS_VideoControlFlags;
````


## -enum-fields
<dl>

### -field KS_VideoControlFlag_FlipHorizontal

<dd>
<p>The minidriver is capable of flipping the image horizontally.</p>
</dd>

### -field KS_VideoControlFlag_FlipVertical

<dd>
<p>The minidriver is capable of flipping the image vertically.</p>
</dd>

### -field KS_Obsolete_VideoControlFlag_ExternalTriggerEnable

<dd>
<p>This value is obsolete. Do not use.</p>
</dd>

### -field KS_Obsolete_VideoControlFlag_Trigger

<dd>
<p>This value is obsolete. Do not use.</p>
</dd>

### -field KS_VideoControlFlag_ExternalTriggerEnable

<dd>
<p>The minidriver can enable acquisition of a single video frame based on an external trigger. An external trigger typically is hardware-specific.</p>
</dd>

### -field KS_VideoControlFlag_Trigger

<dd>
<p>The minidriver can enable acquisition of a single video frame based on a programmatic trigger.</p>
</dd>

### -field KS_VideoControlFlag_IndependentImagePin

<dd>
<p>Determines if the image pin is independent of the video pin.</p>
<p>Supported starting with Windows 8.</p>
</dd>

### -field KS_VideoControlFlag_StillCapturePreviewFrame

<dd>
<p>Reserved for system use. Do not use in your driver.</p>
<p>Supported starting with Windows 8.</p>
</dd>

### -field KS_VideoControlFlag_StartPhotoSequenceCapture

<dd>
<p>Begin photo sequence capture operation.</p>
<p>Supported starting with Windows 8.1.</p>
</dd>

### -field KS_VideoControlFlag_StopPhotoSequenceCapture

<dd>
<p>Stop photo sequence operation.</p>
<p>Supported starting with Windows 8.1.</p>
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
<a href="stream.ksproperty_videocontrol_caps_s">KSPROPERTY_VIDEOCONTROL_CAPS_S</a>
</dt>
<dt>
<a href="stream.ksproperty_videocontrol_mode_s">KSPROPERTY_VIDEOCONTROL_MODE_S</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_VideoControlFlags enumeration%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
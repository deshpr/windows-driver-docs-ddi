---
UID: NI:usbsidebandaudio.IOCTL_USBSBAUD_GET_SIDETONE_VOLUMEPROPERTYVALUES
title: IOCTL_USBSBAUD_GET_SIDETONE_VOLUMEPROPERTYVALUES
author: windows-driver-content
description: TBD
old-location: audio\ioctl_usbsbaud_get_sidetone_volumepropertyvalues.htm
old-project: audio
ms.assetid: 6FF44B7C-2252-45A0-A280-95D844448CF9
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: IOCTL_USBSBAUD_GET_SIDETONE_VOLUMEPROPERTYVALUES, IOCTL_USBSBAUD_GET_SIDETONE_VOLUMEPROPERTYVALUES control, IOCTL_USBSBAUD_GET_SIDETONE_VOLUMEPROPERTYVALUES control code [Audio Devices], audio.ioctl_usbsbaud_get_sidetone_volumepropertyvalues, usbsidebandaudio/IOCTL_USBSBAUD_GET_SIDETONE_VOLUMEPROPERTYVALUES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbsidebandaudio.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	USBSidebandAudio.h
api_name:
-	IOCTL_USBSBAUD_GET_SIDETONE_VOLUMEPROPERTYVALUES
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_USBSBAUD_GET_SIDETONE_VOLUMEPROPERTYVALUES IOCTL


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

TBD


## -ioctlparameters




### -input-buffer

TBD


### -input-buffer-length

TBD


### -output-buffer

TBD


### -output-buffer-length

TBD


### -in-out-buffer

TBD


### -inout-buffer-length

TBD


### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks



TBD




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548651">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548656">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548660">WdfIoTargetSendIoctlSynchronously</a>
 

 


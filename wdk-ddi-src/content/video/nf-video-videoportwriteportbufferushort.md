---
UID: NF:video.VideoPortWritePortBufferUshort
title: VideoPortWritePortBufferUshort function
author: windows-driver-content
description: The VideoPortWritePortBufferUshort function writes a number of USHORT values to a mapped I/O port.
old-location: display\videoportwriteportbufferushort.htm
old-project: display
ms.assetid: d9be3108-27fe-4899-bf23-0f51d9309888
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: VideoPortWritePortBufferUshort, VideoPortWritePortBufferUshort function [Display Devices], VideoPort_Functions_cf88884e-2891-4e82-b7e0-afaa605a2d65.xml, display.videoportwriteportbufferushort, video/VideoPortWritePortBufferUshort
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
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
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: Any level (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortWritePortBufferUshort
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortWritePortBufferUshort function


## -description


The <b>VideoPortWritePortBufferUshort</b> function writes a number of USHORT values to a mapped I/O port.


## -parameters




### -param Port

Pointer to the port. The given <i>Port</i> must be in a mapped I/O-space range returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a>.


### -param Buffer [in]

Pointer to a buffer containing the USHORT values to be written.


### -param Count

Specifies the number of USHORT values to be transferred to the adapter.


## -returns



None




## -remarks



A miniport driver's <a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a> or <a href="https://msdn.microsoft.com/04e3bac6-c905-4c95-bd1b-e85b46c4296d">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortWritePortBufferUshort</b>.

Callers of <b>VideoPortWritePortBufferUshort</b> can be running at any IRQL, provided that the memory pointed to by the <i>Buffer</i> parameter is resident and that pointed to by the <i>Port</i> parameter is resident, mapped device memory.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a>
 

 


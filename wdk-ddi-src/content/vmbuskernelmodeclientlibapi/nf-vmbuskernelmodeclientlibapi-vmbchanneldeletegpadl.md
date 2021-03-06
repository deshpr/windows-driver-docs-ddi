---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelDeleteGpadl
title: VmbChannelDeleteGpadl function
author: windows-driver-content
description: The VmbChannelDeleteGpadl function deletes a Guest Physical Address Descriptor List (GPADL) mapped by the VmbChannelCreateGpadlFromMdl or VmbChannelCreateGpadlFromBuffer functions.
old-location: netvista\vmbchanneldeletegpadl.htm
old-project: netvista
ms.assetid: B1446A29-F2C1-4F08-8B38-5BE9188F5132
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: VmbChannelDeleteGpadl, VmbChannelDeleteGpadl function [Network Drivers Starting with Windows Vista], netvista.vmbchanneldeletegpadl, vmbuskernelmodeclientlibapi/VmbChannelDeleteGpadl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: vmbuskernelmodeclientlibapi.h
req.include-header: VmbusKernelModeClientLibApi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 1.13
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Vmbkmcl.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	vmbkmcl.lib
-	vmbkmcl.dll
api_name:
-	VmbChannelDeleteGpadl
product:
- Windows
targetos: Windows
req.typenames: 
---

# VmbChannelDeleteGpadl function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelDeleteGpadl</b> function deletes a Guest Physical Address Descriptor List (GPADL) mapped by the <a href="https://msdn.microsoft.com/6C63E250-1A11-45E8-B535-263806DA4A33">VmbChannelCreateGpadlFromMdl</a> or
<a href="https://msdn.microsoft.com/B45E2463-1EBC-4F32-B3AD-8331E664BB24">VmbChannelCreateGpadlFromBuffer</a> functions. If the GPADL is currently mapped to the server, this function is blocked until the GPADL is unmapped.


## -parameters




### -param Channel [in]

A handle for a channel.


### -param GpadlHandle [in]

The GPADL handle of the GPADL to delete.


## -returns



This function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/B45E2463-1EBC-4F32-B3AD-8331E664BB24">VmbChannelCreateGpadlFromBuffer</a>



<a href="https://msdn.microsoft.com/6C63E250-1A11-45E8-B535-263806DA4A33">VmbChannelCreateGpadlFromMdl</a>
 

 


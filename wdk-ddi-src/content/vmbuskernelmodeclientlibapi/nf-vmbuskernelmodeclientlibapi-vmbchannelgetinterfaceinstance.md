---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelGetInterfaceInstance
title: VmbChannelGetInterfaceInstance function
author: windows-driver-content
description: The VmbChannelGetInterfaceInstance function gets the active interface instance, which is a GUID that uniquely identifies a channel.
old-location: netvista\vmbchannelgetinterfaceinstance.htm
old-project: netvista
ms.assetid: BEE9581A-5FC4-4C5B-B428-B782E59720C3
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: VmbChannelGetInterfaceInstance, VmbChannelGetInterfaceInstance function [Network Drivers Starting with Windows Vista], netvista.vmbchannelgetinterfaceinstance, vmbuskernelmodeclientlibapi/VmbChannelGetInterfaceInstance
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
-	VmbChannelGetInterfaceInstance
product:
- Windows
targetos: Windows
req.typenames: 
---

# VmbChannelGetInterfaceInstance function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelGetInterfaceInstance</b> function gets the active interface instance, which is a GUID that uniquely identifies a channel.


## -parameters




### -param Channel [in]

The channel for which to get an instance.


### -param InterfaceInstance [out]

A pointer to a GUID, which is the interface instance
of the channel.


## -returns



This function does not return a value.




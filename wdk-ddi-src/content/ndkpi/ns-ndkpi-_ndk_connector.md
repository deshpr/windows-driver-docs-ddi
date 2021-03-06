---
UID: NS:ndkpi._NDK_CONNECTOR
title: "_NDK_CONNECTOR"
author: windows-driver-content
description: The NDK_CONNECTOR structure specifies the attributes of an NDK connector object.
old-location: netvista\ndk_connector.htm
old-project: netvista
ms.assetid: B2E4D369-CCCF-4654-875F-69E90FEA1FF9
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: NDK_CONNECTOR, NDK_CONNECTOR structure [Network Drivers Starting with Windows Vista], PNDK_CONNECTOR, PNDK_CONNECTOR structure pointer [Network Drivers Starting with Windows Vista], _NDK_CONNECTOR, ndkpi/NDK_CONNECTOR, ndkpi/PNDK_CONNECTOR, netvista.ndk_connector
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
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
-	ndkpi.h
api_name:
-	NDK_CONNECTOR
product:
- Windows
targetos: Windows
req.typenames: NDK_CONNECTOR
---

# _NDK_CONNECTOR structure


## -description


The <b>NDK_CONNECTOR</b> structure specifies the attributes of an NDK connector object.


## -struct-fields




### -field Header

The <a href="https://msdn.microsoft.com/library/windows/hardware/hh439928">NDK_OBJECT_HEADER</a> structure for the <b>NDK_CONNECTOR</b> structure. Set the <b>ObjectType</b> member of the structure that <b>Header</b> specifies to <b>NdkObjectTypeConnector</b>.


### -field Dispatch

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/hh439853">NDK_CONNECTOR_DISPATCH</a> structure that defines dispatch functions for the NDK connector object.


## -remarks



An NDK provider must set the <b>Dispatch</b> member pointer to its  <a href="https://msdn.microsoft.com/library/windows/hardware/hh439853">NDK_CONNECTOR_DISPATCH</a> table before returning the created connector object. The provider must not use the <b>Dispatch</b> member after setting it because the NDK consumer can set the <b>Dispatch</b> member to some other value.




## -see-also




<a href="https://msdn.microsoft.com/956D3550-11C8-48D0-BCF4-9027515C7C0E">NDKPI Listeners, Connectors, and Endpoints</a>



<a href="https://msdn.microsoft.com/94993523-D0D7-441E-B95C-417800840BAC">NDKPI Object Lifetime Requirements</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439853">NDK_CONNECTOR_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439863">NDK_FN_CLOSE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439871">NDK_FN_CREATE_COMPLETION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439872">NDK_FN_CREATE_CONNECTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439928">NDK_OBJECT_HEADER</a>
 

 


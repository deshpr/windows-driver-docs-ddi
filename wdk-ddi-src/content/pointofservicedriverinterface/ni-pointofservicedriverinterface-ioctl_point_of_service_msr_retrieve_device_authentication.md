---
UID : NI:pointofservicedriverinterface.IOCTL_POINT_OF_SERVICE_MSR_RETRIEVE_DEVICE_AUTHENTICATION
title : IOCTL_POINT_OF_SERVICE_MSR_RETRIEVE_DEVICE_AUTHENTICATION
author : windows-driver-content
description : This I/O control function retrieves the device authentication type.
old-location : pos\ioctl_point_of_service_msr_retrieve_device_authentication.htm
old-project : pos
ms.assetid : 6f086416-ab50-46fc-933e-a3d48c7dbf4c
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _PosPropertyId, PosPropertyId
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : pointofservicedriverinterface.h
req.include-header : Pointofservicedriverinterface.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IOCTL_POINT_OF_SERVICE_MSR_RETRIEVE_DEVICE_AUTHENTICATION
req.alt-loc : pointofservicedriverinterface.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : PosPropertyId
---

# IOCTL_POINT_OF_SERVICE_MSR_RETRIEVE_DEVICE_AUTHENTICATION IOCTL
This I/O control function retrieves the device authentication type.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
Not used with this operation; set to <b>NULL</b>.

### Input Buffer Length
Not used with this operation; set to <b>0</b> (zero).

### Output Buffer
Pointer to a buffer that receives a <a href="..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_msr_retrieve_device_authentication_data.md">MSR_RETRIEVE_DEVICE_AUTHENTICATION_DATA</a>.

### Output Buffer Length
Size of the output buffer, in bytes. Set to sizeof(<b>MSR_RETRIEVE_DEVICE_AUTHENTICATION_DATA</b>).

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
I/O Status block
Returns <b>TRUE</b> if successful; otherwise, returns <b>FALSE</b>.

To get extended error information, call <a href="http://go.microsoft.com/fwlink/p/?LinkId=316871">GetLastError</a>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | pointofservicedriverinterface.h (include Pointofservicedriverinterface.h) |
| **IRQL** |  |
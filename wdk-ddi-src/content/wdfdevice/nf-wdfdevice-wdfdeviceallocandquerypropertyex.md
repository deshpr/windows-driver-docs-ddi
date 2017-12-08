---
UID: NF.wdfdevice.WdfDeviceAllocAndQueryPropertyEx
title: WdfDeviceAllocAndQueryPropertyEx function
author: windows-driver-content
description: The WdfDeviceAllocAndQueryPropertyEx method allocates a buffer and retrieves a specified device property.
old-location: wdf\wdfdeviceallocandquerypropertyex.htm
old-project: wdf
ms.assetid: 1C1AE0F6-2CAB-4983-B1A7-E6C8BA822754
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WdfDeviceAllocAndQueryPropertyEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.13
req.umdf-ver: 2.0
req.alt-api: WdfDeviceAllocAndQueryPropertyEx
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: APC_LEVEL
req.product: Windows 10 or later.
---

# WdfDeviceAllocAndQueryPropertyEx function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]
The <b>WdfDeviceAllocAndQueryPropertyEx</b> method allocates a buffer and retrieves a specified device property.


## -syntax

````
NTSTATUS WdfDeviceAllocAndQueryPropertyEx(
  _In_     WDFDEVICE                 Device,
  _In_     PWDF_DEVICE_PROPERTY_DATA DeviceProperty,
  _In_     POOL_TYPE                 PoolType,
  _In_opt_ PWDF_OBJECT_ATTRIBUTES    PropertyMemoryAttributes,
  _Out_    WDFMEMORY                 *PropertyMemory,
  _Out_    PDEVPROPTYPE              Type
);
````


## -parameters

### -param Device [in]

A handle to a framework device object.

### -param DeviceProperty [in]

A pointer to a <a href="wdf.wdf_device_property_data">WDF_DEVICE_PROPERTY_DATA</a> structure that identifies the device property to be retrieved.

### -param PoolType [in]

A <a href="kernel.pool_type">POOL_TYPE</a>-typed enumerator that specifies the type of memory to be allocated.

### -param PropertyMemoryAttributes [in, optional]

A pointer to a caller-allocated <a href="wdf.wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that describes object attributes for the memory object that the function will allocate. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.

### -param PropertyMemory [out]

A pointer to a WDFMEMORY-typed location that receives a handle to a framework memory object. 

### -param Type [out]

A pointer to a <b>DEVPROPTYPE</b> variable. If the method is successful, upon return this parameter contains the property type value
                  of the property 
                  data stored in <i>PropertyMemory</i>.

## -returns
If the operation succeeds, <b>WdfDeviceAllocAndQueryPropertyEx</b> returns STATUS_SUCCESS. Additional return values include:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The specified <i>DeviceProperty</i> value is invalid.


 

The method might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.

## -remarks
You can use <b>WdfDeviceAllocAndQueryPropertyEx</b> to retrieve any property that is exposed through the unified property model, whereas the <a href="wdf.wdfdeviceallocandqueryproperty">WdfDeviceAllocAndQueryProperty</a> method only allows querying a subset of the unified property model.

The <b>WdfDeviceAllocAndQueryPropertyEx</b> method determines the amount of memory that is necessary to hold the requested device interface property. It allocates enough memory to hold the data, and returns a handle to a framework memory object that describes the allocated memory. To access the data, your driver can call <a href="wdf.wdfmemorygetbuffer">WdfMemoryGetBuffer</a>.

For information about related methods, see <a href="wdf.accessing_the_unified_device_property_model">Accessing the Unified Device Property Model</a>.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version
</th>
<td width="70%">
1.13
</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version
</th>
<td width="70%">
2.0
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdfdevice.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (KMDF); </dt>
<dt>WUDFx02000.dll (UMDF)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
APC_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdfdeviceallocandqueryinterfaceproperty">WdfDeviceAllocAndQueryInterfaceProperty</a>
</dt>
<dt>
<a href="wdf.wdfdeviceallocandqueryproperty">WdfDeviceAllocAndQueryProperty</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceAllocAndQueryPropertyEx method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
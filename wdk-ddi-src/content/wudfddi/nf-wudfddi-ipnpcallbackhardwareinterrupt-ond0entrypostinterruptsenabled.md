---
UID: NF:wudfddi.IPnpCallbackHardwareInterrupt.OnD0EntryPostInterruptsEnabled
title: IPnpCallbackHardwareInterrupt::OnD0EntryPostInterruptsEnabled (wudfddi.h)
description: A driver's OnD0EntryPostInterruptsEnabled event callback function performs device-specific operations that are required when the driver enables the device's hardware interrupts.
old-location: wdf\ipnpcallbackhardwareinterrupt_ond0entrypostinterruptsenabled.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["IPnpCallbackHardwareInterrupt::OnD0EntryPostInterruptsEnabled"]
ms.keywords: IPnpCallbackHardwareInterrupt interface,OnD0EntryPostInterruptsEnabled method, IPnpCallbackHardwareInterrupt.OnD0EntryPostInterruptsEnabled, IPnpCallbackHardwareInterrupt::OnD0EntryPostInterruptsEnabled, OnD0EntryPostInterruptsEnabled, OnD0EntryPostInterruptsEnabled method, OnD0EntryPostInterruptsEnabled method,IPnpCallbackHardwareInterrupt interface, umdf.ipnpcallbackhardwareinterrupt_ond0entrypostinterruptsenabled, wdf.ipnpcallbackhardwareinterrupt_ond0entrypostinterruptsenabled, wudfddi/IPnpCallbackHardwareInterrupt::OnD0EntryPostInterruptsEnabled
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IPnpCallbackHardwareInterrupt::OnD0EntryPostInterruptsEnabled
 - wudfddi/IPnpCallbackHardwareInterrupt::OnD0EntryPostInterruptsEnabled
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Wudfddi.h
api_name:
 - IPnpCallbackHardwareInterrupt::OnD0EntryPostInterruptsEnabled
---

# IPnpCallbackHardwareInterrupt::OnD0EntryPostInterruptsEnabled


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A driver's <b>OnD0EntryPostInterruptsEnabled</b> event callback function performs device-specific operations that are required when the driver enables the device's hardware interrupts.

## -parameters

### -param pDevice

### -param PreviousState [in]


A <a href="/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_power_device_state">WDF_POWER_DEVICE_STATE</a>-typed enumerator that identifies the previous device power state.


### -param pInterrupt [in]

A pointer to <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice3">IWDFDevice3</a> interface.

## -returns

If successful, <b>OnD0EntryPostInterruptsEnabled</b> returns S_OK. Otherwise, it returns an appropriate failure status.

## -remarks

For more information, see <a href="/windows-hardware/drivers/wdf/enabling-and-disabling-interrupts">Enabling and Disabling Interrupts</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-ipnpcallbackhardwareinterrupt">IPnpCallbackHardwareInterrupt</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallbackhardwareinterrupt-ond0exitpreinterruptsdisabled">OnD0ExitPreInterruptsDisabled</a>


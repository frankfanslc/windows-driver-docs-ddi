---
UID: NF:ntddk.PshedSynchronizeExecution
title: PshedSynchronizeExecution function (ntddk.h)
description: The PshedSynchronizeExecution function synchronizes the execution of a given function with the hardware error processing for an error source.
old-location: whea\pshedsynchronizeexecution.htm
tech.root: whea
ms.date: 02/20/2018
keywords: ["PshedSynchronizeExecution function"]
ms.keywords: PshedSynchronizeExecution, PshedSynchronizeExecution function [WHEA Drivers and Applications], ntddk/PshedSynchronizeExecution, whea.pshedsynchronizeexecution, whearef_7a6363f4-466d-498a-97c4-b5f7937005dd.xml
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
req.lib: Pshed.lib
req.dll: Pshed.dll
req.irql: <= DIRQL
targetos: Windows
req.typenames: 
f1_keywords:
 - PshedSynchronizeExecution
 - ntddk/PshedSynchronizeExecution
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Pshed.dll
api_name:
 - PshedSynchronizeExecution
---

# PshedSynchronizeExecution function


## -description

The <b>PshedSynchronizeExecution</b> function synchronizes the execution of a given function with the hardware error processing for an error source.

## -parameters

### -param ErrorSource [in]


A pointer to a <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_source_descriptor">WHEA_ERROR_SOURCE_DESCRIPTOR</a> structure that describes an error source.

### -param SynchronizeRoutine [in]


A pointer to a caller-supplied function whose execution is synchronized with the hardware error processing for the error source described by the <i>ErrorSource</i> parameter. A <i>SynchronizeRoutine</i> function is declared as follows:


```
BOOLEAN
SynchronizeRoutine(
    _In_ PVOID  SynchronizeContext
    );
```





#### SynchronizeContext

The context value that is passed in the <i>SynchronizeContext</i> parameter to the <b>PshedSynchronizeExecution</b> function.

### -param SynchronizeContext [in]


A pointer to a caller-supplied context area that is passed to the function pointed to by the <i>SynchronizeRoutine</i> parameter.

## -returns

<b>PshedSynchronizeExecution</b> returns the value that is returned by the function pointed to by the <i>SynchronizeRoutine</i> parameter.

## -remarks

A PSHED plug-in calls the <b>PshedSynchronizeExecution</b> function to synchronize the execution of a given function with the hardware error processing for an error source. This is required whenever a PSHED plug-in shares resources between code that executes outside of the normal hardware error processing flow and code that executes as part of the normal hardware error processing flow. For more information about the processing of hardware errors, see <a href="/windows-hardware/drivers/whea/error-processing">Error Processing</a>.

When this function is called, the following occurs:

<ol>
<li>
The IRQL is raised to the IRQL at which the low-level hardware error handler (LLHEH) for the error source executes.

</li>
<li>
Access to the context area specified by the <i>SynchronizeContext</i> parameter is synchronized with the LLHEH by acquiring the associated spin lock.

</li>
<li>
The function specified in the <i>SynchronizeRoutine</i> parameter is called.

</li>
</ol>
Callers of the <b>PshedSynchronizeExecution</b> function must be running at IRQL <= DIRQL, that is, less than or equal to the IRQL at which the LLHEH for the error source executes.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_source_descriptor">WHEA_ERROR_SOURCE_DESCRIPTOR</a>

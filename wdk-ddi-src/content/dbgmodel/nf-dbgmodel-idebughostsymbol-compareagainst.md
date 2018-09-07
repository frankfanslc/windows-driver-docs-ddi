---
UID: NF:dbgmodel.IDebugHostSymbol.CompareAgainst
title: IDebugHostSymbol::CompareAgainst
author: windows-driver-content
description: TBD
ms.assetid: 00afbd6a-9157-43b3-a449-fa9aa6f50fab
ms.author: windowsdriverdev
ms.date: 08/14/2018
ms.topic: method
ms.keywords: IDebugHostSymbol::CompareAgainst, CompareAgainst, IDebugHostSymbol.CompareAgainst, IDebugHostSymbol::CompareAgainst, IDebugHostSymbol.CompareAgainst
req.header: dbgmodel.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	COM
api_location: 
-	dbgmodel.h
api_name: 
-	IDebugHostSymbol.CompareAgainst
product: Windows
targetos: Windows


---

# IDebugHostSymbol::CompareAgainst


## -description

Compares two symbols for equality.  A host is under no obligation to ensure that there is interface pointer equality for two identical symbols.  This can be used to check for equality. 

Note that presently, "comparisonFlags" is reserved.

## -parameters

### -param pComparisonSymbol

### -param comparisonFlags
Reserved.

### -param pMatches


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDebugHostSymbol interface](nn-dbgmodel-idebughostsymbol.md)
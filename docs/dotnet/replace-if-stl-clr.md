---
title: replace_if (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::replace_if
dev_langs:
- C++
helpviewer_keywords:
- replace_if function [STL/CLR]
ms.assetid: 485ed698-551f-4808-8562-9e32b151786d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 6685c2dedc32fbe14febb230cc6d34c6aad14aed
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="replaceif-stlclr"></a>replace_if (STL/CLR)
Sprawdza każdy element w zakresie i zastępuje go, jeśli spełnia określony predykat.  
  
## <a name="syntax"></a>Składnia  
  
```  
template<class _FwdIt, class _Pr, class _Ty> inline  
    void replace_if(_FwdIt _First, _FwdIt _Last, _Pr _Pred,  
        const _Ty% _Val);  
```  
  
## <a name="remarks"></a>Uwagi  
 Ta funkcja działa tak samo jak funkcja standardowa biblioteka C++ `replace_if`. Aby uzyskać więcej informacji, zobacz [replace_if](../standard-library/algorithm-functions.md#replace_if).  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/algorytm >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)
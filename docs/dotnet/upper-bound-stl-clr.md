---
title: upper_bound (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::upper_bound
dev_langs: C++
helpviewer_keywords: upper_bound function [STL/CLR]
ms.assetid: a377a77b-8005-496e-85ae-b431a9b2f0b9
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bcd9cdf28d2d5ff61c081b1670ecc4394158db90
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="upperbound-stlclr"></a>upper_bound (STL/CLR)
Znajduje pozycję pierwszego elementu w uporządkowanym zakresie, który ma wartość większą niż określona wartość, gdzie kryterium sortowania może być określone przez predykat binarny.  
  
## <a name="syntax"></a>Składnia  
  
```  
template<class _FwdIt, class _Ty> inline  
    _FwdIt upper_bound(_FwdIt _First, _FwdIt _Last, const _Ty% _Val);  
template<class _FwdIt, class _Ty, class _Pr> inline  
    _FwdIt upper_bound(_FwdIt _First, _FwdIt _Last,  
        const _Ty% _Val, _Pr _Pred);  
```  
  
## <a name="remarks"></a>Uwagi  
 Ta funkcja działa tak samo jak funkcja standardowa biblioteka C++ `upper_bound`. Aby uzyskać więcej informacji, zobacz [upper_bound](../standard-library/algorithm-functions.md#upper_bound).  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/algorytm >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [Algorytm (STL/CLR)](../dotnet/algorithm-stl-clr.md)
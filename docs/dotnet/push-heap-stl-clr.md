---
title: "push_heap — (STL/CLR) | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::push_heap
dev_langs: C++
helpviewer_keywords: push_heap function [STL/CLR]
ms.assetid: 184fe1d9-5f75-4c11-adbb-84b6b5c8ecd3
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: da6ede7d42f5f431d49951d4e9e69f29ac8541da
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="pushheap-stlclr"></a>push_heap (STL/CLR)
Dodaje element znajdujący się na końcu zakresu do istniejącej sterty, która składa się z poprzednich elementów w zakresie.  
  
## <a name="syntax"></a>Składnia  
  
```  
template<class _RanIt> inline  
    void push_heap(_RanIt _First, _RanIt _Last);  
template<class _RanIt, class _Pr> inline  
    void push_heap(_RanIt _First, _RanIt _Last, _Pr _Pred);  
```  
  
## <a name="remarks"></a>Uwagi  
 Ta funkcja działa tak samo jak funkcja standardowa biblioteka C++ `push_heap`. Aby uzyskać więcej informacji, zobacz [push_heap —](../standard-library/algorithm-functions.md#push_heap).  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/algorytm >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)
---
title: "pop_heap — (STL/CLR) | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::pop_heap
dev_langs: C++
helpviewer_keywords: pop_heap function [STL/CLR]
ms.assetid: d9bde0ed-2122-4d83-b4b3-f47f6fb3729a
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a125eecf32808057f12c4e081e3f73cdde12f736
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="popheap-stlclr"></a>pop_heap (STL/CLR)
Usuwa największy element z przodu sterty do przedostatniej pozycji w zakresie, a następnie tworzy nową stertę z pozostałych elementów.  
  
## <a name="syntax"></a>Składnia  
  
```  
template<class _RanIt> inline  
    void pop_heap(_RanIt _First, _RanIt _Last);  
template<class _RanIt, class _Pr> inline  
    void pop_heap(_RanIt _First, _RanIt _Last, _Pr _Pred);  
```  
  
## <a name="remarks"></a>Uwagi  
 Ta funkcja działa tak samo jak funkcja standardowa biblioteka C++ `pop_heap`. Aby uzyskać więcej informacji, zobacz [pop_heap —](../standard-library/algorithm-functions.md#pop_heap).  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/algorytm >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)
---
title: next_permutation (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::next_permutation
dev_langs: C++
helpviewer_keywords: next_permutation function [STL/CLR]
ms.assetid: e36e821f-4b8d-461b-8074-69cd0175ccec
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 073aef1aa8e18ecbefe0c0816785c4f67af84244
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="nextpermutation-stlclr"></a>next_permutation (STL/CLR)
Zmienia kolejność elementów w zakresie, tak że oryginalna kolejność jest zastąpiona przez leksykograficznie kolejną większą permutację, o ile takowa istnieje, gdzie sens „kolejna” może być określony przez predykat binarny.  
  
## <a name="syntax"></a>Składnia  
  
```  
template<class _BidIt> inline  
    bool next_permutation(_BidIt _First, _BidIt _Last);  
template<class _BidIt, class _Pr> inline  
    bool next_permutation(_BidIt _First, _BidIt _Last, _Pr _Pred);  
```  
  
## <a name="remarks"></a>Uwagi  
 Ta funkcja działa tak samo jak funkcja standardowa biblioteka C++ `next_permutation`. Aby uzyskać więcej informacji, zobacz [next_permutation](../standard-library/algorithm-functions.md#next_permutation).  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/algorytm >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [Algorytm (STL/CLR)](../dotnet/algorithm-stl-clr.md)
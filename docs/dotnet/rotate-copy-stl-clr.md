---
title: rotate_copy (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::rotate_copy
dev_langs:
- C++
helpviewer_keywords:
- rotate_copy function [STL/CLR]
ms.assetid: ed697552-130f-474f-9ab6-133332bb2587
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e9535280a9e03c6472609069898ad214914330f2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="rotatecopy-stlclr"></a>rotate_copy (STL/CLR)
Wymienia elementy w dwóch sąsiednich zakresach w ramach zakresu źródłowego i kopiuje wynik do zakresu docelowego.  
  
## <a name="syntax"></a>Składnia  
  
```  
template<class _FwdIt, class _OutIt> inline  
    _OutIt rotate_copy(_FwdIt _First, _FwdIt _Mid, _FwdIt _Last,  
        _OutIt _Dest);  
```  
  
## <a name="remarks"></a>Uwagi  
 Ta funkcja działa tak samo jak funkcja standardowa biblioteka C++ `rotate_copy`. Aby uzyskać więcej informacji, zobacz [rotate_copy](../standard-library/algorithm-functions.md#rotate_copy).  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/algorytm >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)
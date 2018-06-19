---
title: find_first_of — (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::find_first_of
dev_langs:
- C++
helpviewer_keywords:
- find_first_of function [STL/CLR]
ms.assetid: d559bad4-fc12-4201-af49-db0e7eec48e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 6c86ed89e9affa12cc4bb15d0d473f3ef8434101
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33110123"
---
# <a name="findfirstof-stlclr"></a>find_first_of (STL/CLR)
Wyszukuje pierwsze wystąpienie którejś z kilku wartości w zakresie docelowym lub pierwsze wystąpienie któregoś z kilku elementów, które są równoważne w sensie określonym przez predykat binarny dla określonego zestawu elementów.  
  
## <a name="syntax"></a>Składnia  
  
```  
template<class _FwdIt1, class _FwdIt2> inline  
    _FwdIt1 find_first_of(_FwdIt1 _First1, _FwdIt1 _Last1,  
        _FwdIt2 _First2, _FwdIt2 _Last2);  
template<class _FwdIt1, class _FwdIt2, class _Pr> inline  
    _FwdIt1 find_first_of(_FwdIt1 _First1, _FwdIt1 _Last1,  
        _FwdIt2 _First2, _FwdIt2 _Last2, _Pr _Pred);  
```  
  
## <a name="remarks"></a>Uwagi  
 Ta funkcja działa tak samo jak funkcja standardowa biblioteka C++ `find_first_of`. Aby uzyskać więcej informacji, zobacz [find_first_of](../standard-library/algorithm-functions.md#find_first_of).  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/algorytm >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)
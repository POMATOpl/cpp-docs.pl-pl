---
title: Przydziel | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- allocate_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], allocate
- allocate __declspec keyword
ms.assetid: 67828b31-de60-4c0e-b0a6-ef3aab22641d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 82ce0af801b77a9566bd6395a9f03b05f41676d7
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408519"
---
# <a name="allocate"></a>allocate
**Microsoft Specific**  
  
 **Przydzielić** Specyfikator deklaracji nazwy segmentu danych, w którym będzie można przydzielić elementu danych.  
  
## <a name="syntax"></a>Składnia  
  
```  
   __declspec(allocate("segname")) declarator  
```  
  
## <a name="remarks"></a>Uwagi  
 Nazwa *segname* musi być zadeklarowana przy użyciu jednej z następujące pragmy:  
  
-   [code_seg](../preprocessor/code-seg.md)  
  
-   [const_seg](../preprocessor/const-seg.md)  
  
-   [data_seg](../preprocessor/data-seg.md)  
  
-   [init_seg](../preprocessor/init-seg.md)  
  
-   [sekcja](../preprocessor/section.md)  
  
## <a name="example"></a>Przykład  
  
```cpp 
// allocate.cpp  
#pragma section("mycode", read)  
__declspec(allocate("mycode"))  int i = 0;  
  
int main() {  
}  
```  
  
 **END specyficzny dla Microsoft**  
  
## <a name="see-also"></a>Zobacz także  
 [__declspec](../cpp/declspec.md)   
 [Słowa kluczowe](../cpp/keywords-cpp.md)
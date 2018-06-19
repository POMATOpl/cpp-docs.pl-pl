---
title: Kompilatora (poziom 4) ostrzeżenie C4816 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4816
dev_langs:
- C++
helpviewer_keywords:
- C4816
ms.assetid: 60f730ae-d942-4db9-ab97-41d4a874d8da
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 74386e980171ce1b54c8256ad505b363df7830d8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33303592"
---
# <a name="compiler-warning-level-4-c4816"></a>Kompilator C4816 ostrzegawcze (poziom 4)
"param": parametr ma zerowy rozmiar tablicy, która zostanie obcięta (chyba że obiekt jest przekazywana przez odwołanie)  
  
 Parametr do obiektu z tablicą o rozmiarze zerowym nie został przekazany przez odwołanie. Tablicy nie będą uzyskać kopiowane, gdy obiekt został przekazany.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład generuje C4816:  
  
```  
// C4816.cpp  
// compile with: /W4  
#include <stdio.h>  
  
extern "C" int printf_s(const char *, ...);  
  
#pragma warning(disable : 4200)  
  
struct S1  
{  
    int i;  
    char cArr[];  
};  
  
void TestErr(S1 s1)   // C4816 param with zero-array   
                      // not passed by reference  
{  
    printf_s("%d %c %c\n", s1.i, s1.cArr[0], s1.cArr[1]);  
}  
  
void TestOk(S1 &s1)  
{  
    printf_s("%d %c %c\n", s1.i, s1.cArr[0], s1.cArr[1]);  
}  
  
int main()  
{  
    S1 myS_1 = { 6, 'a', 'b', 'c' };  
    TestErr(myS_1);  
    TestOk(myS_1);  
}  
```
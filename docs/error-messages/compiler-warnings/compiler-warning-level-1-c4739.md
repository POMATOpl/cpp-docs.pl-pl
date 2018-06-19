---
title: Kompilatora (poziom 1) ostrzeżenie C4739 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4739
dev_langs:
- C++
helpviewer_keywords:
- C4739
ms.assetid: 600873b3-7c85-4cd4-944e-cd8e01bfcbb0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c90acdbc8ab32522e8e7cfac079547caaf84398d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33281908"
---
# <a name="compiler-warning-level-1-c4739"></a>Kompilator C4739 ostrzegawcze (poziom 1)
Odwołanie do zmiennej "var" przekracza jego miejsce do magazynowania  
  
 Wartość została przypisana do zmiennej, ale wartość jest większa niż rozmiar zmiennej. Pamięć zostanie zapisany poza zmiennej lokalizacji pamięci i możliwa jest utrata danych.  
  
 Aby usunąć to ostrzeżenie, tylko przypisać wartości do zmiennej, którego rozmiar może obsłużyć wartość.  
  
 Poniższy przykład generuje C4739:  
  
```  
// C4739.cpp  
// compile with: /RTCs /Zi /W1 /c  
char *pc;  
int main() {  
   char c;  
   *(int *)&c = 1;   // C4739  
  
   // OK  
   *(char *)&c = 1;  
}  
```
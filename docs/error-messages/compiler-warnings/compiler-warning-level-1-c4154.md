---
title: Kompilator ostrzeżenie (poziom 1) C4154 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4154
dev_langs:
- C++
helpviewer_keywords:
- C4154
ms.assetid: 4511afeb-e893-4cc6-83b6-4c7a0477f76b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8cdb93f5bc7e4ef099b4e05bb92673abe9d36e7f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46063635"
---
# <a name="compiler-warning-level-1-c4154"></a>Kompilator ostrzeżenie (poziom 1) C4154

Usunięcie wyrażenia tablicowego; dostarczono konwersji do wskaźnika

Nie można użyć `delete` w tablicy, dlatego kompilator konwertuje tablicy do wskaźnika.

## <a name="example"></a>Przykład

```
// C4154.cpp
// compile with: /c /W1
int main() {
   int array[ 10 ];
   delete array;   // C4154 can't delete stack object

   int *parray2 = new int [10];
   int (&array2)[10] = (int(&)[10]) parray2;
   delete [] array2;   // C4154

   // try the following line instead
   delete [] &array2;
}
```
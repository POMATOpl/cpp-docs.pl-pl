---
title: C3162 błąd kompilatora | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3162
dev_langs:
- C++
helpviewer_keywords:
- C3162
ms.assetid: 0d4c4a24-1456-4191-b7d8-c38cb7b17c32
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9b1527e56bbd834f2ebea9c51f82bb55c05da52d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3162"></a>C3162 błąd kompilatora
'type': Typ referencyjny, który posiada destruktor nie może służyć jako typ elementu członkowskiego danych statycznych "członek"  
  
 Środowisko uruchomieniowe języka wspólnego nie wiedzieć, kiedy uruchomić destruktor zdefiniowany przez użytkownika, gdy klasa zawiera także statycznej funkcji członkowskiej.  
  
 Destruktor nigdy nie zostanie uruchomiony, chyba że jawnie usunąć obiektu.  
  
 Aby uzyskać więcej informacji, zobacz,  
  
-   [/clr (Kompilacja środowiska uruchomieniowego języka wspólnego)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Typowe problemy przy migracji Visual C++ w wersji 64-bitowej](../../build/common-visual-cpp-64-bit-migration-issues.md)  
  
## <a name="example"></a>Przykład  
 Poniższy przykład generuje C3162.  
  
```  
// C3162.cpp  
// compile with: /clr /c  
ref struct A {  
   ~A() { System::Console::WriteLine("in destructor"); }  
   static A i;   // C3162  
   static A^ a = gcnew A;   // OK  
};  
  
int main() {  
   A ^ a = gcnew A;  
   delete a;  
}  
```
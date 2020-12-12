---
description: 'Dowiedz się więcej o: błąd kompilatora C3073'
title: Błąd kompilatora C3073
ms.date: 11/04/2016
f1_keywords:
- C3073
helpviewer_keywords:
- C3073
ms.assetid: b24b9b8b-f9fb-4c3c-a1a0-97fad2081bfc
ms.openlocfilehash: e26938d6c708c364bb2447b793abf7d51adb5779
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320250"
---
# <a name="compiler-error-c3073"></a>Błąd kompilatora C3073

"Type": Klasa ref nie ma zdefiniowanego przez użytkownika konstruktora kopiującego

W kompilacji [/CLR (Kompilacja środowiska uruchomieniowego języka wspólnego)](../../build/reference/clr-common-language-runtime-compilation.md) kompilator nie będzie generował konstruktora kopiującego dla typu referencyjnego. W dowolnej kompilacji **/CLR** należy zdefiniować własny Konstruktor kopiujący dla typu referencyjnego, jeśli oczekuje się, że wystąpienie typu ma zostać skopiowane.

Aby uzyskać więcej informacji, zobacz [semantyka stosu języka C++ dla typów referencyjnych](../../dotnet/cpp-stack-semantics-for-reference-types.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C3073.

```cpp
// C3073.cpp
// compile with: /clr
ref class R {
public:
   R(int) {}
};

ref class S {
public:
   S(int) {}
   S(const S %rhs) {}   // copy constructor
};

void f(R) {}
void f2(S) {}
void f3(R%){}

int main() {
   R r(1);
   f(r);   // C3073
   f3(r);   // OK

   S s(1);
   f2(s);   // OK
}
```

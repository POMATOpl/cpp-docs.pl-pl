---
description: 'Dowiedz się więcej na temat: Ostrzeżenie kompilatora C4959'
title: Ostrzeżenie kompilatora C4959
ms.date: 11/04/2016
f1_keywords:
- C4959
helpviewer_keywords:
- C4959
ms.assetid: 3a128f3e-4d8a-4565-ba1a-5d32fdeb5982
ms.openlocfilehash: 3a4fae04ee654caf23776a7bf4d6b073853bd03a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336083"
---
# <a name="compiler-warning-c4959"></a>Ostrzeżenie kompilatora C4959

> nie można zdefiniować niezarządzanej struktury "*Type*" w/CLR: Safe, ponieważ dostęp do jej elementów członkowskich daje kod niemożliwy do zweryfikowania

## <a name="remarks"></a>Uwagi

Uzyskanie dostępu do elementu członkowskiego typu niezarządzanego spowoduje utworzenie obrazu niemożliwy do zweryfikowania (peverify.exe).

Aby uzyskać więcej informacji, zobacz [czysty i możliwy do zweryfikowania kod (C++/CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).

Opcja " **/CLR: Safe** Compiler" jest przestarzała w programie visual Studio 2015 i nie jest obsługiwana w programie visual Studio 2017.

To ostrzeżenie jest wydawane jako błąd i można je wyłączyć za pomocą dyrektywy pragma [Warning](../../preprocessor/warning.md) lub opcji kompilatora [/WD](../../build/reference/compiler-option-warning-level.md) .

## <a name="example"></a>Przykład

Poniższy przykład generuje C4959:

```cpp
// C4959.cpp
// compile with: /clr:safe

// Uncomment the following line to resolve.
// #pragma warning( disable : 4959 )
struct X {
   int data;
};

int main() {
   X x;
   x.data = 10;   // C4959
}
```

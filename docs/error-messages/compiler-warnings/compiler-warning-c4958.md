---
description: 'Dowiedz się więcej na temat: Ostrzeżenie kompilatora C4958'
title: Ostrzeżenie kompilatora C4958
ms.date: 11/04/2016
f1_keywords:
- C4958
helpviewer_keywords:
- C4958
ms.assetid: e79b9e9c-d572-4a3a-a3b6-60962b70864a
ms.openlocfilehash: 1a6260a441b619923e8c2ddf8c7a5d891a3c3844
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314805"
---
# <a name="compiler-warning-c4958"></a>Ostrzeżenie kompilatora C4958

> "*Operation*": arytmetyka wskaźnika nie jest możliwa do zweryfikowania

## <a name="remarks"></a>Uwagi

Użycie funkcji arytmetycznej wskaźnika spowoduje utworzenie obrazu, który będzie możliwy do zweryfikowania.

Aby uzyskać więcej informacji, zobacz [czysty i możliwy do zweryfikowania kod (C++/CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).

Opcja " **/CLR: Safe** Compiler" jest przestarzała w programie visual Studio 2015 i nie jest obsługiwana w programie visual Studio 2017.

To ostrzeżenie jest wydawane jako błąd i można je wyłączyć za pomocą dyrektywy pragma [Warning](../../preprocessor/warning.md) lub opcji kompilatora [/WD](../../build/reference/compiler-option-warning-level.md) .

## <a name="example"></a>Przykład

Poniższy przykład generuje C4958:

```cpp
// C4958.cpp
// compile with: /clr:safe
// #pragma warning( disable : 4958 )
using namespace System;

int main( ) {
   Int32 arr[] = new Int32[10];
   Int32* p = &arr[0];
   p++;   // C4958
}
```

Kompilator implementuje operacje tablicowe przy użyciu arytmetycznego wskaźnika. W związku z tym tablice natywne nie są możliwe do zweryfikowania; Zamiast tego użyj tablicy CLR. Aby uzyskać więcej informacji, zobacz [Array](../../extensions/arrays-cpp-component-extensions.md).

Poniższy przykład generuje C4958:

```cpp
// C4958b.cpp
// compile with: /clr:safe
// #pragma warning( disable : 4958 )

int main() {
   int array[5];
   array[4] = 0;   // C4958
}
```

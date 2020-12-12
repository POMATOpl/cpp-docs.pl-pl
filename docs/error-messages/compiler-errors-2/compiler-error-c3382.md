---
description: 'Dowiedz się więcej o: błąd kompilatora C3382'
title: Błąd kompilatora C3382
ms.date: 11/04/2016
f1_keywords:
- C3382
helpviewer_keywords:
- C3382
ms.assetid: a7603abd-ac4e-4ae6-a02b-3bdc6d1908a6
ms.openlocfilehash: 582a807ac43d6110fb0f19aef5806e4118516db2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285659"
---
# <a name="compiler-error-c3382"></a>Błąd kompilatora C3382

element "sizeof" nie jest obsługiwany z/CLR: Safe

Plik wyjściowy **/CLR: Safe** kompilacja jest plikiem, który jest typu "bezpieczna", a sizeof nie jest obsługiwana, ponieważ zwracana wartość operatora sizeof jest size_t, którego rozmiar zmienia się w zależności od systemu operacyjnego.

Aby uzyskać więcej informacji, zobacz,

- [sizeof — Operator](../../cpp/sizeof-operator.md)

- [/CLR (Kompilacja środowiska uruchomieniowego języka wspólnego)](../../build/reference/clr-common-language-runtime-compilation.md)

- [Typowe problemy przy migracji Visual C++ w wersji 64-bitowej](../../build/common-visual-cpp-64-bit-migration-issues.md)

## <a name="example"></a>Przykład

Poniższy przykład generuje C3382.

```cpp
// C3382.cpp
// compile with: /clr:safe
int main() {
   sizeof( char );   // C3382
}
```

---
description: 'Dowiedz się więcej o: błąd kompilatora C3383'
title: Błąd kompilatora C3383
ms.date: 11/04/2016
f1_keywords:
- C3383
helpviewer_keywords:
- C3383
ms.assetid: ceb7f725-f417-4dc3-8496-0f413bb76687
ms.openlocfilehash: fb5baf99c6738db1296cf4fb0a509c63d570ad78
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285594"
---
# <a name="compiler-error-c3383"></a>Błąd kompilatora C3383

element "operator new" nie jest obsługiwany z/CLR: Safe

Plik wyjściowy **/CLR: Safe** kompilacja jest plikiem, który jest typu "bezpieczna", a wskaźniki nie są obsługiwane.

Aby uzyskać więcej informacji, zobacz,

- [/CLR (Kompilacja środowiska uruchomieniowego języka wspólnego)](../../build/reference/clr-common-language-runtime-compilation.md)

- [Typowe problemy przy migracji Visual C++ w wersji 64-bitowej](../../build/common-visual-cpp-64-bit-migration-issues.md)

## <a name="example"></a>Przykład

Poniższy przykład generuje C3383.

```cpp
// C3383.cpp
// compile with: /clr:safe
int main() {
   char* pCharArray = new char[256];  // C3383
}
```

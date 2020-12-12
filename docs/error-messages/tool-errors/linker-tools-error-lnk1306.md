---
description: 'Dowiedz się więcej na temat: Błąd narzędzi konsolidatora LNK1306'
title: Błąd narzędzi konsolidatora LNK1306
ms.date: 11/04/2016
f1_keywords:
- LNK1306
helpviewer_keywords:
- LNK1306
ms.assetid: fad1df6a-0bd9-412f-b0d1-7c9bc749c584
ms.openlocfilehash: aa6386da7c836eea8365d8a4ffde0bbd80d0fa81
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193659"
---
# <a name="linker-tools-error-lnk1306"></a>Błąd narzędzi konsolidatora LNK1306

> Funkcja punktu wejścia biblioteki DLL nie może być zarządzana; Kompiluj do natywnego

`DllMain` nie można kompilować do MSIL; musi być skompilowany do natywny.

Aby rozwiązać ten problem,

- Kompiluj plik zawierający punkt wejścia bez **/CLR**.

- Umieść punkt wejścia w `#pragma unmanaged` sekcji.

Aby uzyskać więcej informacji, zobacz:

- [/CLR (Kompilacja środowiska uruchomieniowego języka wspólnego)](../../build/reference/clr-common-language-runtime-compilation.md)

- [zarządzane, niezarządzane](../../preprocessor/managed-unmanaged.md)

- [Inicjowanie zestawów mieszanych](../../dotnet/initialization-of-mixed-assemblies.md)

- [Zachowanie biblioteki wykonawczej DLL i Visual C++](../../build/run-time-library-behavior.md)

## <a name="example"></a>Przykład

Poniższy przykład generuje LNK1306.

```cpp
// LNK1306.cpp
// compile with: /clr /link /dll /entry:NewDllMain
// LNK1306 error expected
#include <windows.h>
int __stdcall NewDllMain( HINSTANCE h, ULONG ulReason, PVOID pvReserved ) {
   return 1;
}
```

Aby rozwiązać ten problem, nie używaj opcji/CLR do kompilowania tego pliku lub Użyj `#pragma` dyrektywy, aby umieścić definicję punktu wejścia w niezarządzanej sekcji, jak pokazano w tym przykładzie:

```cpp
// LNK1306fix.cpp
// compile with: /clr /link /dll /entry:NewDllMain
#include <windows.h>
#pragma managed(push, off)
int __stdcall NewDllMain( HINSTANCE h, ULONG ulReason, PVOID pvReserved ) {
   return 1;
}
#pragma managed(pop)
```

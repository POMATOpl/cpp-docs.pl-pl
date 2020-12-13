---
description: 'Dowiedz się więcej na temat: definicje i deklaracje (C++)'
title: Definicje i deklaracje (C++)
ms.date: 11/04/2016
ms.assetid: 56b809c0-e602-4f18-9ca5-cd7a8fbaaf30
ms.openlocfilehash: c22274534193011c1c5ec26aedbece339a9302b4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339439"
---
# <a name="definitions-and-declarations-c"></a>Definicje i deklaracje (C++)

**Specyficzne dla firmy Microsoft**

Interfejs DLL odwołuje się do wszystkich elementów (funkcji i danych), które są znane do wyeksportowania przez jakiś program w systemie. oznacza to, że wszystkie elementy, które są zadeklarowane jako **`dllimport`** lub **`dllexport`** . Wszystkie deklaracje zawarte w interfejsie DLL muszą określać **`dllimport`** **`dllexport`** atrybut lub. Jednak definicja musi określać tylko **`dllexport`** atrybut. Na przykład następująca definicja funkcji generuje błąd kompilatora:

```
__declspec( dllimport ) int func() {   // Error; dllimport
                                       // prohibited on definition.
   return 1;
}
```

Ten kod również generuje błąd:

```
__declspec( dllimport ) int i = 10;  // Error; this is a definition.
```

Jest to jednak poprawna składnia:

```
__declspec( dllexport ) int i = 10;  // Okay--export definition
```

Użycie **`dllexport`** wskazuje definicję, a mimo to **`dllimport`** oznacza deklarację. Musisz użyć **`extern`** słowa kluczowego with, **`dllexport`** Aby wymusić deklarację; w przeciwnym razie jest implikowana definicja. W ten sposób następujące przykłady są poprawne:

```
#define DllImport   __declspec( dllimport )
#define DllExport   __declspec( dllexport )

extern DllExport int k; // These are both correct and imply a
DllImport int j;        // declaration.
```

W poniższych przykładach wyjaśnimy powyższe:

```
static __declspec( dllimport ) int l; // Error; not declared extern.

void func() {
    static __declspec( dllimport ) int s;  // Error; not declared
                                           // extern.
    __declspec( dllimport ) int m;         // Okay; this is a
                                           // declaration.
    __declspec( dllexport ) int n;         // Error; implies external
                                           // definition in local scope.
    extern __declspec( dllimport ) int i;  // Okay; this is a
                                           // declaration.
    extern __declspec( dllexport ) int k;  // Okay; extern implies
                                           // declaration.
    __declspec( dllexport ) int x = 5;     // Error; implies external
                                           // definition in local scope.
}
```

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[dllexport, dllimport](../cpp/dllexport-dllimport.md)

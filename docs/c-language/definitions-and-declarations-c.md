---
description: 'Dowiedz się więcej na temat: definicje i deklaracje (C)'
title: Definicje i deklaracje (C)
ms.date: 11/04/2016
helpviewer_keywords:
- export functions
ms.assetid: d150395a-89d4-4298-9ac4-08f84fe1261c
ms.openlocfilehash: a88a0e56e68b052e3bb8759f9c40670379bd2628
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186860"
---
# <a name="definitions-and-declarations-c"></a>Definicje i deklaracje (C)

**Specyficzne dla firmy Microsoft**

Interfejs DLL odwołuje się do wszystkich elementów (funkcji i danych), które są znane do wyeksportowania przez jakiś program w systemie. oznacza to, że wszystkie elementy, które są zadeklarowane jako **`dllimport`** lub `dllexport` . Wszystkie deklaracje zawarte w interfejsie DLL muszą określać **`dllimport`** `dllexport` atrybut lub. Jednak definicja może określać tylko `dllexport` atrybut. Na przykład następująca definicja funkcji generuje błąd kompilatora:

```
#define DllImport   __declspec( dllimport )
#define DllExport   __declspec( dllexport )

DllImport int func()    /* Error; dllimport prohibited in */
                        /* definition. */
{
   return 1;
}
```

Ten kod również generuje błąd:

```
#define DllImport   __declspec( dllimport )
#define DllExport   __declspec( dllexport )

DllImport int i = 10;      /* Error; this is a definition. */
```

Jest to jednak poprawna składnia:

```
#define DllImport   __declspec( dllimport )
#define DllExport   __declspec( dllexport )

DllExport int i = 10;      /* Okay: this is an export definition. */
```

Użycie `dllexport` wskazuje definicję, a mimo to **`dllimport`** oznacza deklarację. Musisz użyć **`extern`** słowa kluczowego with, `dllexport` Aby wymusić deklarację; w przeciwnym razie jest implikowana definicja.

```
#define DllImport   __declspec( dllimport )
#define DllExport   __declspec( dllexport )

extern DllImport int k;   /* These are correct and imply */
Dllimport int j;          /* a declaration. */
```

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje importowania i eksportowania biblioteki DLL](../c-language/dll-import-and-export-functions.md)

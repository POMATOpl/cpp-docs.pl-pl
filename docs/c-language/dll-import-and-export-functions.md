---
description: 'Dowiedz się więcej na temat: funkcje importowania i eksportowania biblioteki DLL'
title: Importowanie bibliotek DLL i eksportowanie funkcji
ms.date: 11/04/2016
helpviewer_keywords:
- DLLs [C++], importing
- dllimport attribute [C++], storage-class attribute
- DLL exports [C++]
- declaring functions, with dllexport and dllimport
- extended storage-class attributes
- dllexport attribute [C++], storage-class attribute
ms.assetid: 08d164b9-770a-4e14-afeb-c6f21d9e33e4
ms.openlocfilehash: 9f734d4415b473717ad8cd7c94213f1beaff9dc8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213933"
---
# <a name="dll-import-and-export-functions"></a>Importowanie bibliotek DLL i eksportowanie funkcji

**Specyficzne dla firmy Microsoft**

Najbardziej kompletne i aktualne informacje na ten temat można znaleźć w [dllexport, dllimport](../cpp/dllexport-dllimport.md).

**`dllimport`** `dllexport` Modyfikatory klasy magazynu i są rozszerzeniami specyficznymi dla firmy Microsoft do języka C. Te Modyfikatory jawnie definiują interfejs biblioteki DLL dla klienta (plik wykonywalny lub inna Biblioteka DLL). Deklarowanie funkcji jako `dllexport` eliminuje potrzebę definicji modułów (. DEF). Można również używać **`dllimport`** `dllexport` modyfikatorów i z danymi i obiektami.

**`dllimport`** `dllexport` Modyfikatory klasy magazynu i muszą być używane z słowem kluczowym składni atrybutów rozszerzonych, **`__declspec`** jak pokazano w poniższym przykładzie:

```
#define DllImport   __declspec( dllimport )
#define DllExport   __declspec( dllexport )

DllExport void func();
DllExport int i = 10;
DllExport int j;
DllExport int n;
```

Aby uzyskać szczegółowe informacje na temat składni dla rozszerzonych modyfikatorów klasy magazynu, zobacz [atrybuty rozszerzone Storage-Class](../c-language/c-extended-storage-class-attributes.md).

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Definicje funkcji języka C](../c-language/c-function-definitions.md)

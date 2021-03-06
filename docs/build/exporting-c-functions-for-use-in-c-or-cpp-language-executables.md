---
description: 'Dowiedz się więcej na temat: Eksportowanie funkcji języka C do użycia w plikach wykonywalnych w języku C lub C++'
title: Eksportowanie funkcji języka C do użycia w plikach wykonywalnych języka C lub C++
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C], exporting
- functions [C], C or C++ executables and
- __cplusplus macro
- exporting DLLs [C++], C functions in C++ executables
- exporting functions [C++], C functions in C++ executables
ms.assetid: b51d6e5e-37cf-4c1c-b0bf-fcf188c82f00
ms.openlocfilehash: 9a45eb0a6f2a73f89696c03325690bc82ecd3082
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97156661"
---
# <a name="exporting-c-functions-for-use-in-c-or-c-language-executables"></a>Eksportowanie funkcji języka C do użycia w plikach wykonywalnych języka C lub C++

Jeśli masz funkcje w bibliotece DLL, którą chcesz uzyskać dostęp z poziomu języka C lub modułu języka C++, należy użyć makra preprocesora **__cplusplus** , aby określić, który język jest kompilowany, a następnie zadeklarować te funkcje przy użyciu połączenia C, jeśli są używane z poziomu modułu języka C++. W przypadku użycia tej techniki i udostępnienia plików nagłówkowych dla biblioteki DLL te funkcje mogą być używane przez użytkowników C i C++ bez zmian.

Poniższy kod przedstawia plik nagłówka, który może być używany przez aplikacje klienckie C i C++:

```h
// MyCFuncs.h
#ifdef __cplusplus
extern "C" {  // only need to export C interface if
              // used by C++ source code
#endif

__declspec( dllimport ) void MyCFunc();
__declspec( dllimport ) void AnotherCFunc();

#ifdef __cplusplus
}
#endif
```

Jeśli chcesz połączyć funkcje C z plikiem wykonywalnym języka C++, a pliki nagłówka deklaracji funkcji nie używały powyższej techniki, w pliku źródłowym języka C++ wykonaj następujące czynności, aby uniemożliwić kompilatorowi dekorowania nazwy nazw funkcji C:

```cpp
extern "C" {
#include "MyCHeader.h"
}
```

## <a name="what-do-you-want-to-do"></a>Co chcesz zrobić?

- [Eksportowanie z biblioteki DLL za pomocą plików. def](exporting-from-a-dll-using-def-files.md)

- [Eksportowanie z biblioteki DLL przy użyciu __declspec (dllexport)](exporting-from-a-dll-using-declspec-dllexport.md)

- [Eksportowanie i importowanie przy użyciu AFX_EXT_CLASS](exporting-and-importing-using-afx-ext-class.md)

- [Wybieranie metody eksportowania do użycia](determining-which-exporting-method-to-use.md)

- [Importowanie do aplikacji przy użyciu atrybutu __declspec(dllimport)](importing-into-an-application-using-declspec-dllimport.md)

- [Inicjowanie biblioteki DLL](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Jak chcesz dowiedzieć się więcej?

- [Nazwy ozdobione](reference/decorated-names.md)

- [Użycie zewnętrznie w celu określenia powiązania](../cpp/extern-cpp.md)

## <a name="see-also"></a>Zobacz też

[Eksportowanie z biblioteki DLL](exporting-from-a-dll.md)

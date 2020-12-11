---
description: 'Dowiedz się więcej na temat: Importowanie do aplikacji przy użyciu __declspec (dllimport)'
title: Importowanie do aplikacji przy użyciu atrybutu __declspec(dllimport)
ms.date: 11/04/2016
helpviewer_keywords:
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: edb4da4e-f83a-44cf-a668-9239d49dbe42
ms.openlocfilehash: 946ec6b4b06b22dd7dd68be2478a0b0571aa641c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97156180"
---
# <a name="import-into-an-application-using-__declspecdllimport"></a>Importowanie do aplikacji przy użyciu atrybutu __declspec(dllimport)

Program, który używa symboli publicznych zdefiniowanych przez bibliotekę DLL, jest określany do zaimportowania. Podczas tworzenia plików nagłówkowych dla aplikacji, które używają bibliotek DLL do kompilowania za pomocą programu, użyj **`__declspec(dllimport)`** na deklaracjach symboli publicznych. Słowo kluczowe **`__declspec(dllimport)`** działa bez względu na to, czy eksportujesz pliki. def, czy za pomocą **`__declspec(dllexport)`** słowa kluczowego.

Aby kod był bardziej czytelny, zdefiniuj makro dla, **`__declspec(dllimport)`** a następnie użyj makra, aby zadeklarować każdy zaimportowany symbol:

```
#define DllImport   __declspec( dllimport )

DllImport int  j;
DllImport void func();
```

Użycie **`__declspec(dllimport)`** jest opcjonalne w deklaracjach funkcji, ale kompilator generuje bardziej wydajny kod, jeśli używasz tego słowa kluczowego. Należy jednak użyć **`__declspec(dllimport)`** do importowania pliku wykonywalnego, aby uzyskać dostęp do publicznych symboli i obiektów danych biblioteki DLL. Należy pamiętać, że użytkownicy biblioteki DLL nadal muszą łączyć się z biblioteką importu.

Można użyć tego samego pliku nagłówka zarówno dla biblioteki DLL, jak i aplikacji klienckiej. W tym celu należy użyć specjalnego symbolu preprocesora, który wskazuje, czy tworzysz bibliotekę DLL, czy kompilujesz aplikację kliencką. Na przykład:

```
#ifdef _EXPORTING
   #define CLASS_DECLSPEC    __declspec(dllexport)
#else
   #define CLASS_DECLSPEC    __declspec(dllimport)
#endif

class CLASS_DECLSPEC CExampleA : public CObject
{ ... class definition ... };
```

## <a name="what-do-you-want-to-do"></a>Co chcesz zrobić?

- [Inicjowanie biblioteki DLL](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Jak chcesz dowiedzieć się więcej?

- [Importowanie i eksportowanie funkcji śródwierszowych](importing-and-exporting-inline-functions.md)

- [Importy wzajemne](mutual-imports.md)

## <a name="see-also"></a>Zobacz też

[Importowanie do aplikacji](importing-into-an-application.md)

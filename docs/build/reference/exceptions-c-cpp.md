---
title: Kody wyjątków ładowania biblioteki DLL (CC++/)
ms.date: 11/19/2019
f1_keywords:
- ERROR_MOD_NOT_FOUND
- vcppException
- ERROR_SEVERITY_ERROR
helpviewer_keywords:
- vcppException
- C++ exception handling, delayed loading of DLLs
- delayed loading of DLLs, exceptions
- ERROR_SEVERITY_ERROR exception
- ERROR_MOD_NOT_FOUND exception
ms.assetid: c03be05d-1c39-4f35-84cf-00c9af3bae9a
ms.openlocfilehash: f557fe736f45f8c3f5411d076a0be18f1d1b670e
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2019
ms.locfileid: "74243849"
---
# <a name="exceptions-cc"></a>Wyjątki (C/C++)

Po napotkaniu błędów mogą być zgłaszane dwa kody wyjątków:

- W przypadku błędu funkcji **LoadLibrary**

- Dla błędu **GetProcAddress**

Oto informacje o wyjątku:

```
//
// Exception information
//
#define FACILITY_VISUALCPP  ((LONG)0x6d)
#define VcppException(sev,err)  ((sev) | (FACILITY_VISUALCPP<<16) | err)
```

Zgłoszone kody wyjątków to standardowe wartości VcppException (ERROR_SEVERITY_ERROR, ERROR_MOD_NOT_FOUND) i VcppException (ERROR_SEVERITY_ERROR ERROR_PROC_NOT_FOUND). Wyjątek przekazuje wskaźnik do struktury **DelayLoadInfo** w wartości LPDWORD, która może zostać pobrana przez **GetExceptionInformation** w strukturze [EXCEPTION_RECORD](/windows/win32/api/winnt/ns-winnt-exception_record) , ExceptionInformation [0].

Ponadto jeśli w polu grAttrs zostanie ustawiona niepoprawna liczba bitów, zostanie zgłoszony wyjątek ERROR_INVALID_PARAMETER. Ten wyjątek dotyczy wszystkich intencji i celów, które są krytyczne.

Zobacz [struktury i definicje stałe,](structure-and-constant-definitions.md) Aby uzyskać więcej informacji.

## <a name="see-also"></a>Zobacz także

[Obsługa błędów oraz powiadomienia](error-handling-and-notification.md)

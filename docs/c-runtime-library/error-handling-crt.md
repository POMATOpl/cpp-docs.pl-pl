---
description: Dowiedz się więcej o obsłudze błędów (CRT)
title: Obsługa błędów (CRT)
ms.date: 11/04/2016
helpviewer_keywords:
- error handling, C routines for
- logic errors
- error handling, library routines
- testing, for program errors
ms.assetid: 125ac697-9eb0-4152-a440-b7842f23d97f
ms.openlocfilehash: 4aa81f1152fe991398b38f6b433993aecb8be401
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331148"
---
# <a name="error-handling-crt"></a>Obsługa błędów (CRT)

Użyj tych procedur, aby obsłużyć błędy programu.

## <a name="error-handling-routines"></a>Procedury obsługi błędów

|Procedura|Zastosowanie|
|-------------|---------|
|[Assert](../c-runtime-library/reference/assert-macro-assert-wassert.md) — makro|Testowanie błędów logiki programowania; dostępne zarówno w wersji wersji, jak i debugowej biblioteki wykonawczej.|
|[_ASSERT, _ASSERTE](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) makra|Podobnie jak w przypadku **potwierdzeń**, ale dostępne tylko w wersjach debugowych biblioteki wykonawczej.|
|[clearerr](../c-runtime-library/reference/clearerr.md)|Resetuj wskaźnik błędu. Wywołanie funkcji **szybkiego przewijania** lub zamknięcia strumienia powoduje także zresetowanie wskaźnika błędu.|
|[_eof](../c-runtime-library/reference/eof.md)|Sprawdź koniec pliku w operacji we/wy niskiego poziomu.|
|[feof](../c-runtime-library/reference/feof.md)|Testuj pod kątem końca pliku. Koniec pliku jest również wskazywany, gdy **_read** zwraca 0.|
|[ferror](../c-runtime-library/reference/ferror.md)|Testowanie błędów we/wy strumienia.|
|[_RPT, _RPTF](../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) makra|Wygeneruj raport podobny do **printf**, ale jest dostępny tylko w wersjach debugowania biblioteki wykonawczej.|
|[_set_error_mode](../c-runtime-library/reference/set-error-mode.md)|Modyfikuje **__error_mode** , aby określić lokalizację niedomyślną, w której czas wykonywania C zapisuje komunikat o błędzie, który może spowodować zakończenie tego programu.|
|[_set_purecall_handler](../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md)|Ustawia program obsługi dla czystego wywołania funkcji wirtualnej.|

## <a name="see-also"></a>Zobacz też

- [Procedury środowiska uruchomieniowego języka Universal C według kategorii](../c-runtime-library/run-time-routines-by-category.md)

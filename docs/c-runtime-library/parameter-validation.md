---
title: Sprawdzanie poprawności parametru
description: Opis weryfikacji parametrów w bibliotece środowiska uruchomieniowego Microsoft C.
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- parameters, validation
ms.assetid: 019dd5f0-dc61-4d2e-b4e9-b66409ddf1f2
ms.openlocfilehash: 8378e4bf9bdfc950002c3ed8c3ef50c27a3c162d
ms.sourcegitcommit: 30792632548d1c71894f9fecbe2f554294b86020
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/06/2020
ms.locfileid: "91765262"
---
# <a name="parameter-validation"></a>Sprawdzanie poprawności parametru

Większość funkcji CRT z rozszerzonymi zabezpieczeniami i wielu, które nie, sprawdzają poprawność ich parametrów dla elementów, takich jak sprawdzanie wskaźników dla **wartości null**, liczby całkowite mieszczą się w prawidłowym zakresie lub że wartości wyliczenia są prawidłowe. W przypadku znalezienia nieprawidłowego parametru zostanie wywołana procedura obsługi nieprawidłowego parametru.

## <a name="invalid-parameter-handler-routine"></a>Nieprawidłowa procedura procedury obsługi parametrów

Gdy funkcja biblioteki środowiska uruchomieniowego języka C wykrywa nieprawidłowy parametr, przechwytuje pewne informacje o błędzie, a następnie wywołuje makro, które otacza funkcję wysyłania procedury obsługi nieprawidłowego parametru. Będzie to jeden z [_invalid_parameter](../c-runtime-library/reference/invalid-parameter-functions.md), [_invalid_parameter_noinfo](../c-runtime-library/reference/invalid-parameter-functions.md)lub [_invalid_parameter_noinfo_noreturn](../c-runtime-library/reference/invalid-parameter-functions.md). Funkcja wysyłania wywoływana jest zależna od tego, czy kod jest odpowiednio, Kompilacja debugowania, kompilacja detaliczna lub błąd nie jest uważany za odzyskiwalny.

W kompilacjach debugowania makro nieprawidłowego parametru zazwyczaj wywołuje nieudane potwierdzenie i punkt przerwania debugera przed wywołaniem funkcji wysyłania. Gdy kod jest wykonywany, potwierdzenie może zostać zgłoszone użytkownikowi w oknie dialogowym zawierającym "Abort", "ponów" i "Kontynuuj" lub podobne opcje w zależności od systemu operacyjnego i wersji biblioteki środowiska uruchomieniowego. Te opcje umożliwiają użytkownikowi natychmiastowe zakończenie działania programu, w celu dołączenia debugera lub poinformowanie o istniejącym kodzie, który wywołuje funkcję wysyłania.

Funkcja wysyłania nieprawidłowego parametru wywołuje aktualnie przypisaną procedurę obsługi nieprawidłowego parametru. Domyślnie nieprawidłowe wywołania parametrów `_invoke_watson` , które powodują zamknięcie aplikacji i generują miniy zrzut. Jeśli jest włączona przez system operacyjny, okno dialogowe monituje użytkownika o wysłanie zrzutu awaryjnego do firmy Microsoft w celu przeprowadzenia analizy.

Można zmienić to zachowanie przy użyciu funkcji [_set_invalid_parameter_handler](../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) lub [_set_thread_local_invalid_parameter_handler](../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) , aby ustawić procedurę obsługi nieprawidłowego parametru na własną funkcję. Jeśli określona funkcja nie kończy działanie aplikacji, formant jest zwracany do funkcji, która otrzymała nieprawidłowe parametry. W CRT te funkcje zwykle zatrzymają wykonywanie funkcji, ustawimy `errno` Kod błędu i zwracają kod błędu. W wielu przypadkach `errno` wartość i wartość zwracana są oba `EINVAL` , aby wskazać nieprawidłowy parametr. W niektórych przypadkach zwracany jest bardziej szczegółowy kod błędu, taki jak `EBADF` dla nieprawidłowego wskaźnika pliku przekazana jako parametr.

Aby uzyskać więcej informacji na temat `errno` , zobacz [errno, _doserrno, _sys_errlist i _sys_nerr](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="see-also"></a>Zobacz też

[Funkcje zabezpieczeń w CRT](../c-runtime-library/security-features-in-the-crt.md)\
[Funkcje biblioteki CRT](../c-runtime-library/crt-library-features.md)

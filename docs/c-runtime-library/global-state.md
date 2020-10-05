---
title: Stan globalny w środowisku CRT
description: Opisuje sposób obsługi udostępnionego stanu globalnego w środowisku uruchomieniowym Microsoft Universal C.
ms.topic: conceptual
ms.date: 10/02/2020
helpviewer_keywords:
- CRT global state
ms.openlocfilehash: 6c8b97e2bd6fa71891aedacb1fbfec2bbe382d84
ms.sourcegitcommit: faedcc3be78b29c78e5d51e3c7c7c2f448c745bf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/05/2020
ms.locfileid: "91717518"
---
# <a name="global-state-in-the-crt"></a>Stan globalny w środowisku CRT

Niektóre funkcje w środowisku uruchomieniowym uniwersalnego języka C (UCRT) używają stanu globalnego. Na przykład `setlocale()` ustawia ustawienia regionalne dla całego programu, które mają wpływ na separatory cyfr, stronę kodową tekstu i tak dalej.

Globalny stan UCRT nie jest współużytkowany przez aplikacje i system operacyjny. Na przykład, jeśli aplikacja jest wywoływana `setlocale()` , nie wpłynie to na ustawienia regionalne dla żadnych składników systemu operacyjnego, które korzystają z czasu wykonywania C, lub w inny sposób.

## <a name="os-specific-versions-of-crt-functions"></a>Wersje funkcji CRT specyficzne dla systemu operacyjnego

W UCRT funkcje, które współdziałają ze stanem globalnym, mają funkcję "sznurka", poprzedzoną prefiksem `_o_` . Na przykład:

- `setlocale()` wpływa na globalny stan specyficzny dla aplikacji.
- `_o_setlocale()` ma wpływ na stan globalny współużytkowany przez wszystkie składniki systemu operacyjnego, ale nie aplikacje.

Jedyną różnicą między tymi funkcjami "sznurka" jest to, że podczas odczytywania/zapisywania globalnego stanu CRT wersje specyficzne dla systemu operacyjnego (czyli wersje, które zaczynają się od `_o_` ) używają kopii systemu operacyjnego stanu globalnego zamiast kopii stanu globalnego aplikacji.

Wersje tych funkcji, które są specyficzne dla systemu operacyjnego, są w systemie `ucrt.osmode.lib` . Na przykład wersja systemu operacyjnego `setlocale()` jest `_o_setlocale()`

Istnieją dwa sposoby odizolowania stanu CRT składnika ze stanu CRT aplikacji:

- Statycznie Połącz składnik przy użyciu opcji kompilatora `/MT` (Release) lub `/MTd` (Debug). Aby uzyskać szczegółowe informacje, zobacz [/MD,/MT,/LD](../build/reference/md-mt-ld-use-run-time-library.md). Łączenie statyczne może znacznie zwiększyć rozmiar binarny.
- Począwszy od systemu Windows 10 w wersji 2004, dynamicznie łącz się z CRT, ale Wywołaj Eksporty w trybie systemu operacyjnego (funkcje zaczynające się od _o_). Aby wywoływać Eksporty w trybie systemu operacyjnego, należy je statycznie łączyć jak wcześniej, ale zignorować statyczne UCRT przy użyciu opcji konsolidatora `/NODEFAULTLIB:libucrt.lib` (Release) lub `/NODEFAULTLIB:libucrtd.lib` (Debug). I Dodaj `ucrt.osmode.lib` do danych wejściowych konsolidatora. Aby uzyskać szczegółowe informacje, zobacz [/NODEFAULTLIB (Ignoruj biblioteki)](../build/reference/nodefaultlib-ignore-libraries.md) .

> [!Note]
> W kodzie źródłowym, Zapisz `setlocale()` , nie `_o_setlocale()` . `ucrt.osmode.lib`Łącząc się z, konsolidator automatycznie zastępuje wersję funkcji specyficzną dla systemu operacyjnego. Oznacza to, że `setlocale()` zostanie zastąpiony `_o_setlocale()` .

Łączenie przed `ucrt.osmode.lib` wyłącza niektóre wywołania UCRT, które są dostępne tylko w trybie aplikacji. Próba wywołania tych wyników spowoduje błąd łącza.

## <a name="global-state-affected-by-appos-separation"></a>Stan globalny, na który ma wpływ separacja aplikacji/systemu operacyjnego

Stan globalny, na który mają wpływ rozdzielenie stanu aplikacji i systemu operacyjnego:

- [Dane regionalne](locale.md)
- Programy obsługi sygnałów ustawione przez [sygnał](reference/signal.md)
- Procedury zakończenia ustawione przez [zakończenie](reference/set-terminate-crt.md)
- [errno i _doserrno](errno-doserrno-sys-errlist-and-sys-nerr.md)
- Losowy stan generowania liczb używany przez [Rand](reference/rand.md) i [srand](reference/srand.md)
- Funkcje, które zwracają bufor, którego użytkownik nie musi wydać:   [strtok, wcstok, _mbstok](reference/strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md) [tmpnam, _wtmpnam](reference/tempnam-wtempnam-tmpnam-wtmpnam.md) [asctime, _wasctime](reference/asctime-wasctime.md) [gmtime, _gmtime32, _gmtime64](reference/gmtime-gmtime32-gmtime64.md) [_fcvt](reference/fcvt.md) [_ecvt](reference/ecvt.md) [strerror, _strerror, _wcserror, __wcserror](reference/strerror-strerror-wcserror-wcserror.md)
- Bufor używany przez [_putch, _putwch](reference/putch-putwch.md)
- [_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)
- [_set_new_handler](reference/set-new-handler.md) i [_set_new_mode](reference/set-new-mode.md)
- [fmode](text-and-binary-mode-file-i-o.md)
- [Informacje o strefie czasowej](time-management.md)

## <a name="see-also"></a>Zobacz też

[Dokumentacja biblioteki wykonawczej języka C](c-run-time-library-reference.md)

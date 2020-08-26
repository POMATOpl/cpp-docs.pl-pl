---
title: vprintf — Funkcje
ms.date: 11/04/2016
api_location:
- msvcr110.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr80.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- vprintf
helpviewer_keywords:
- vprintf function
- formatted text [C++]
ms.assetid: 02ac7c51-eab1-4bf0-bf4c-77065e3fa744
ms.openlocfilehash: 2455655404bd61c220ebe4e3d018bc81204fa51e
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845370"
---
# <a name="vprintf-functions"></a>vprintf — Funkcje

Każda `vprintf` Funkcja przyjmuje wskaźnik do listy argumentów, a następnie formatuje i zapisuje dane w konkretnym miejscu docelowym. Funkcje te różnią się w wykonaniu walidacji parametru, niezależnie od tego, czy funkcje są ciągami znaków dwubajtowych, wyjściowymi, a także obsługą określania kolejności, w której parametry są używane w ciągu formatu.

[_vcprintf, _vcwprintf](../c-runtime-library/reference/vcprintf-vcprintf-l-vcwprintf-vcwprintf-l.md)\
[vfprintf, vfwprintf](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)\
[_vfprintf_p, _vfprintf_p_l, _vfwprintf_p _vfwprintf_p_l](../c-runtime-library/reference/vfprintf-p-vfprintf-p-l-vfwprintf-p-vfwprintf-p-l.md)\
[vfprintf_s, _vfprintf_s_l, vfwprintf_s _vfwprintf_s_l](../c-runtime-library/reference/vfprintf-s-vfprintf-s-l-vfwprintf-s-vfwprintf-s-l.md)\
[vprintf —, vwprintf](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)\
[_vprintf_p, _vprintf_p_l, _vwprintf_p _vwprintf_p_l](../c-runtime-library/reference/vprintf-p-vprintf-p-l-vwprintf-p-vwprintf-p-l.md)\
[vprintf_s, _vprintf_s_l, vwprintf_s _vwprintf_s_l](../c-runtime-library/reference/vprintf-s-vprintf-s-l-vwprintf-s-vwprintf-s-l.md)\
[_vscprintf, _vscprintf_l, _vscwprintf _vscwprintf_l](../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)\
[_vsnprintf, _vsnwprintf](../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md) 
 [vsprintf, vswprintf](../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md)\
[_vsprintf_p, _vsprintf_p_l, _vswprintf_p _vswprintf_p_l](../c-runtime-library/reference/vsprintf-p-vsprintf-p-l-vswprintf-p-vswprintf-p-l.md)\
[vsprintf_s, _vsprintf_s_l, vswprintf_s, _vswprintf_s_l](../c-runtime-library/reference/vsprintf-s-vsprintf-s-l-vswprintf-s-vswprintf-s-l.md)

## <a name="remarks"></a>Uwagi

`vprintf`Funkcje są podobne do ich odpowiedników funkcji wymienionych w poniższej tabeli. Jednakże każda `vprintf` funkcja akceptuje wskaźnik do listy argumentów, podczas gdy każda z tych funkcji akceptuje listę argumentów.

Te funkcje formatują dane wyjściowe do miejsc docelowych w następujący sposób.

|Funkcja|Funkcja odpowiadająca|Miejsce docelowe danych wyjściowych|Sprawdzanie poprawności parametru|Obsługa parametrów pozycyjnych|
|--------------|--------------------------|------------------------|--------------------------|----------------------------------|
|`_vcprintf`|[_cprintf](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)|console|Sprawdź, czy nie ma wartości null.|nie|
|`_vcwprintf`|[_cwprintf](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)|console|Sprawdź, czy nie ma wartości null.|nie|
|`vfprintf`|[fprintf —](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|*Strumień*|Sprawdź, czy nie ma wartości null.|nie|
|**vfprintf_p**|[fprintf_p](../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)|*Strumień*|Sprawdź, czy format ma wartość null i jest prawidłowy.|tak|
|`vfprintf_s`|[fprintf_s](../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)|*Strumień*|Sprawdź, czy format ma wartość null i jest prawidłowy.|nie|
|`vfwprintf`|[fwprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|*Strumień*|Sprawdź, czy nie ma wartości null.|nie|
|**vfwprintf_p**|[fwprintf_p](../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)|*Strumień*|Sprawdź, czy format ma wartość null i jest prawidłowy.|tak|
|`vfwprintf_s`|[fwprintf_s](../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)|*Strumień*|Sprawdź, czy format ma wartość null i jest prawidłowy.|nie|
|`vprintf`|[printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|`Stdout`|Sprawdź, czy nie ma wartości null.|nie|
|**vprintf_p**|[printf_p](../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)|`Stdout`|Sprawdź, czy format ma wartość null i jest prawidłowy.|tak|
|`vprintf_s`|[printf_s](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|`Stdout`|Sprawdź, czy format ma wartość null i jest prawidłowy.|nie|
|`vwprintf`|[wprintf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|`Stdout`|Sprawdź, czy nie ma wartości null.|nie|
|**vwprintf_p**|[wprintf_p](../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)|`Stdout`|Sprawdź, czy format ma wartość null i jest prawidłowy.|tak|
|`vwprintf_s`|[wprintf_s](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|`Stdout`|Sprawdź, czy format ma wartość null i jest prawidłowy.|nie|
|**vsprintf**|[sprintf —](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)|pamięć wskazywana przez *bufor*|Sprawdź, czy nie ma wartości null.|nie|
|**vsprintf_p**|[sprintf_p](../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)|pamięć wskazywana przez *bufor*|Sprawdź, czy format ma wartość null i jest prawidłowy.|tak|
|`vsprintf_s`|[sprintf_s](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)|pamięć wskazywana przez *bufor*|Sprawdź, czy format ma wartość null i jest prawidłowy.|nie|
|`vswprintf`|[swprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)|pamięć wskazywana przez *bufor*|Sprawdź, czy nie ma wartości null.|nie|
|**vswprintf_p**|[swprintf_p](../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)|pamięć wskazywana przez *bufor*|Sprawdź, czy format ma wartość null i jest prawidłowy.|tak|
|`vswprintf_s`|[swprintf_s](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)|pamięć wskazywana przez *bufor*|Sprawdź, czy format ma wartość null i jest prawidłowy.|nie|
|`_vscprintf`|[_vscprintf](../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)|pamięć wskazywana przez *bufor*|Sprawdź, czy nie ma wartości null.|nie|
|`_vscwprintf`|[_vscwprintf](../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)|pamięć wskazywana przez *bufor*|Sprawdź, czy nie ma wartości null.|nie|
|`_vsnprintf`|[_snprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)|pamięć wskazywana przez *bufor*|Sprawdź, czy nie ma wartości null.|nie|
|`_vsnwprintf`|[_snwprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)|pamięć wskazywana przez *bufor*|Sprawdź, czy nie ma wartości null.|nie|

`argptr`Argument ma typ `va_list` , który jest zdefiniowany w elemencie VarArgs. H i STDARG. C. `argptr`Zmienna musi być inicjowana przez **va_start** i może zostać zainicjowana przez kolejne wywołania, a `va_arg` `argptr` następnie wskazuje początek listy argumentów konwertowanych i przesyłanych do danych wyjściowych zgodnie z odpowiednimi specyfikacjami w argumencie *Format* . *Format* ma taką samą formę i funkcję jak argument *formatu* dla [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md). Żadna z tych funkcji nie jest uruchamiana `va_end` . Aby zapoznać się z bardziej szczegółowym opisem każdej `vprintf` funkcji, zobacz opis jej funkcji odpowiadającej powyższej tabeli.

`_vsnprintf` różni się od **vsprintf** w tym, że zapisuje nie więcej niż *Count* bajtów do *buforu*.

Wersje tych funkcji **z wrostkowe w** nazwie są wersjami znaków dwubajtowych odpowiednich funkcji **bez wrostkowe;** w każdej z tych funkcji o szerokim znaku *bufor* i *Format* są ciągami znaków dwubajtowych. W przeciwnym razie każda funkcja o szerokim znaku zachowuje się identycznie z jej odpowiednikiem funkcji SBCS.

Wersje tych funkcji z sufiksów **_s** i **_p** są bezpieczniejszymi wersjami. Te wersje sprawdzają poprawność ciągów formatowania i wygenerują wyjątek, jeśli ciąg formatu nie jest poprawnie sformułowany (na przykład jeśli użyto nieprawidłowych znaków formatowania).

Wersje tych funkcji z sufiksem **_p** zapewniają możliwość określenia kolejności, w której podane argumenty są zastępowane w ciągu formatu. Aby uzyskać więcej informacji, zobacz [Printf_p parametry pozycyjne](../c-runtime-library/printf-p-positional-parameters.md).

W przypadku **vsprintf**, `vswprintf` , `_vsnprintf` i `_vsnwprintf` , jeśli kopiowanie odbywa się między ciągami, które nakładają się, zachowanie jest niezdefiniowane.

> [!IMPORTANT]
> Upewnij się, że *Format* nie jest ciągiem zdefiniowanym przez użytkownika. Aby uzyskać więcej informacji, zobacz [unikanie przekroczeń buforu](/windows/win32/SecBP/avoiding-buffer-overruns). Jeśli używane są bezpieczne wersje tych funkcji (sufiksy **_s** lub **_p** ), ciąg formatu dostarczony przez użytkownika może wyzwolić wyjątek nieprawidłowego parametru, jeśli podany przez użytkownika ciąg zawiera nieprawidłowe znaki formatowania.

## <a name="see-also"></a>Zobacz też

[We/Wy strumienia](../c-runtime-library/stream-i-o.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf —, _sprintf_l, swprintf, _swprintf_l, \_ _swprintf_l](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[va_arg, va_copy, va_end, va_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)

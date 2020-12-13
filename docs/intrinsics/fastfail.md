---
description: 'Dowiedz się więcej na temat: __fastfail'
title: __fastfail
ms.date: 09/02/2019
ms.assetid: 9cd32639-e395-4c75-9f3a-ac3ba7f49921
ms.openlocfilehash: c7521f10dee7602fae3de5b2ac6fcc0245214bec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336986"
---
# <a name="__fastfail"></a>__fastfail

**Specyficzne dla firmy Microsoft**

Natychmiast kończy proces wywołujący z minimalnym obciążeniem.

## <a name="syntax"></a>Składnia

```C
void __fastfail(unsigned int code);
```

### <a name="parameters"></a>Parametry

*kodu*\
podczas `FAST_FAIL_<description>` Symboliczna stała z pliku Winnt. h lub WDM. h, która wskazuje przyczynę zakończenia procesu.

## <a name="return-value"></a>Wartość zwracana

`__fastfail`Wewnętrzna nie zwraca.

## <a name="remarks"></a>Uwagi

`__fastfail`Wewnętrznie udostępnia mechanizm *szybkiego żądania niepowodzenia* — sposób, w jaki proces potencjalnie uszkodzony może zażądać natychmiastowego zakończenia procesu. Krytyczne błędy, które mogą mieć uszkodzony stan programu i stosu poza odzyskiwaniem, nie mogą być obsługiwane przez funkcję regularnego obsługi wyjątków. Użyj `__fastfail` , aby przerwać proces przy użyciu minimalnego obciążenia.

Wewnętrznie program `__fastfail` jest implementowany przy użyciu kilku mechanizmów specyficznych dla architektury:

|Architektura|Instrukcja|Lokalizacja argumentu kodu|
|------------------|-----------------|-------------------------------|
|x86|int 0x29|`ecx`|
|x64|int 0x29|`rcx`|
|ARM|0xDEFB kodu operacji|`r0`|
|ARM64|0xF003 kodu operacji|`x0`|

Szybkie żądanie niepowodzenia jest samodzielne i zwykle wymaga wykonania tylko dwóch instrukcji. Po wykonaniu szybkiego żądania niepowodzenia jądro podejmuje odpowiednie działanie. W kodzie trybu użytkownika nie ma żadnych zależności pamięci poza wskaźnikiem instrukcji, gdy zostanie zgłoszone zdarzenie szybkiego błędu. To maksymalizuje swoją niezawodność, nawet w przypadku poważnych uszkodzeń pamięci.

`code`Argument, jeden ze `FAST_FAIL_<description>` stałych symbolicznych z Winnt. h lub WDM. h, opisuje typ warunku niepowodzenia. Jest on włączany do raportów o błędach w sposób specyficzny dla środowiska.

Szybkie błędy w trybie użytkownika są wyświetlane jako wyjątek, który nie jest ciągły, z kodem wyjątku 0xC0000409 oraz co najmniej jeden parametr wyjątku. Pierwszy parametr wyjątku jest `code` wartością. Ten kod wyjątku wskazuje na Raportowanie błędów systemu Windows (raportowanie błędów) i infrastrukturę debugowania, że proces jest uszkodzony, a w odpowiedzi na awarię należy podjąć minimalne akcje w procesie. Żądania szybkiego niepowodzenia w trybie jądra są implementowane przy użyciu dedykowanego kodu wykrywania `KERNEL_SECURITY_CHECK_FAILURE` (0x139). W obu przypadkach nie są wywoływane programy obsługi wyjątków, ponieważ oczekuje się, że program jest w stanie uszkodzenia. Jeśli jest obecny debuger, ma możliwość sprawdzenia stanu programu przed zakończeniem.

Obsługa natywnego, wbudowanego mechanizmu awarii systemu Windows 8. Systemy operacyjne Windows, które nie obsługują instrukcji Fast Fail, natywnie zazwyczaj traktują szybkie żądanie niepowodzenia jako naruszenie zasad dostępu lub jako dane `UNEXPECTED_KERNEL_MODE_TRAP` wykrywania. W takich przypadkach program jest nadal zakończony, ale nie musi być szybko.

`__fastfail` jest dostępny tylko jako wewnętrzny.

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__fastfail`|x86, x64, ARM, ARM64|

**Plik nagłówka**\<intrin.h>

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)

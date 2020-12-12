---
description: 'Dowiedz się więcej na temat: stałe "Commit-to-Disk"'
title: Stałe typu commit-to-disk
ms.date: 11/04/2016
f1_keywords:
- vc.constants
helpviewer_keywords:
- commit-to-disk constants
ms.assetid: 0b903b23-b4fa-431e-a937-51d95f695ecf
ms.openlocfilehash: 416729f4b3b7bfdfdcb0ba11193f6c2a52691e6e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322649"
---
# <a name="commit-to-disk-constants"></a>Stałe typu commit-to-disk

**Specyficzne dla firmy Microsoft**

## <a name="syntax"></a>Składnia

```
#include <stdio.h>
```

## <a name="remarks"></a>Uwagi

Te stałe specyficzne dla firmy Microsoft określają, czy bufor skojarzony z otwartym plikiem jest opróżniany do buforów systemu operacyjnego, czy do dysku. Tryb jest dołączony do ciągu określającego typ dostępu do odczytu/zapisu (**"r"**, **"w"**, **"a"**, **"r +"**, **"w +"**, **"a +"**).

Tryby zatwierdzania na dysku są następujące:

- **s**

   Zapisuje zapisaną zawartość określonego buforu na dysku. Ta funkcja commit-to-Disk występuje tylko w jawnych wywołaniach funkcji [fflush](../c-runtime-library/reference/fflush.md) lub [_flushall](../c-runtime-library/reference/flushall.md) . Ten tryb jest przydatny podczas pracy z danymi poufnymi. Na przykład jeśli program kończy pracę po wywołaniu `fflush` lub `_flushall` , można upewnić się, że dane osiągnęły bufory systemu operacyjnego. Jednak jeśli plik nie zostanie otwarty z opcją **c** , dane mogą nigdy nie przetworzyć go na dysku w przypadku przerwania systemu operacyjnego.

- **n**

   Zapisuje zapisaną zawartość określonego buforu do buforów systemu operacyjnego. System operacyjny może buforować dane, a następnie określić optymalny czas zapisywania na dysku. W wielu warunkach takie zachowanie sprawia, że jest to efektywne zachowanie programu. Jednakże jeśli przechowywanie danych ma krytyczne znaczenie (takie jak transakcje bankowe lub informacje o biletach lotniczych), należy rozważyć użycie opcji **c** . Tryb **n** jest wartością domyślną.

> [!NOTE]
> Opcje **c** i **n** nie są częścią standardu ANSI dla `fopen` , ale są rozszerzeniami firmy Microsoft i nie powinny być używane w przypadku potrzeby przenoszenia w formacie ANSI.

## <a name="using-the-commit-to-disk-feature-with-existing-code"></a>Korzystanie z funkcji Zatwierdź do dysku z istniejącym kodem

Domyślnie wywołania funkcji biblioteki [fflush](../c-runtime-library/reference/fflush.md) lub [_flushall](../c-runtime-library/reference/flushall.md) zapisują dane do buforów obsługiwanych przez system operacyjny. System operacyjny określa optymalny czas zapisu danych na dysku. Funkcja zatwierdzania na dysku w bibliotece wykonawczej pozwala zagwarantować, że krytyczne dane są zapisywane bezpośrednio na dysku, a nie w buforach systemu operacyjnego. Tę możliwość można przekazać do istniejącego programu bez ponownego zapisywania, łącząc jego pliki obiektów z TOWARami. OBJ.

W utworzonym pliku wykonywalnym program wywołuje `fflush` zapis zawartości buforu bezpośrednio na dysku, a następnie wywołuje, aby `_flushall` zapisać zawartość wszystkich buforów na dysku. Te dwie funkcje są jedynymi wpływem towaru. OBJ.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[We/Wy strumienia](../c-runtime-library/stream-i-o.md)<br/>
[_fdopen, _wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)<br/>
[fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md)<br/>
[Stałe globalne](../c-runtime-library/global-constants.md)

---
description: 'Dowiedz się więcej na temat: _purecall'
title: _purecall
ms.date: 4/2/2020
api_name:
- _purecall
- _o__purecall
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ntoskrnl.exe
- ucrtbase.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- purecall
- _purecall
helpviewer_keywords:
- _purecall function
- purecall function
ms.assetid: 56135d9b-3403-4e22-822d-e714523801cc
ms.openlocfilehash: df52d7383685f3ce183562d8789b710fd7587acd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209454"
---
# <a name="_purecall"></a>_purecall

Domyślna procedura obsługi błędów wywołania funkcji wirtualnej. Kompilator generuje kod, aby wywołać tę funkcję w przypadku wywołania czystej wirtualnej funkcji członkowskiej.

## <a name="syntax"></a>Składnia

```C
extern "C" int __cdecl _purecall();
```

## <a name="remarks"></a>Uwagi

Funkcja **_purecall** jest szczegółową implementacją kompilatora języka Microsoft C++ specyficzną dla firmy Microsoft. Ta funkcja nie jest przeznaczona do wywoływania bezpośrednio przez kod i nie ma deklaracji nagłówka publicznego. Jest on udokumentowany w tym miejscu, ponieważ jest publicznym eksportem biblioteki środowiska uruchomieniowego języka C.

Wywołanie czystej funkcji wirtualnej jest błędem, ponieważ nie ma implementacji. Kompilator generuje kod, aby wywołać funkcję programu obsługi błędów **_purecall** w przypadku wywołania czystej funkcji wirtualnej. Domyślnie **_purecall** kończy program. Przed zakończeniem funkcja **_purecall** wywołuje funkcję **_purecall_handler** , jeśli została ona ustawiona dla procesu. Możesz zainstalować własną funkcję obsługi błędów dla czystych wywołań funkcji wirtualnych, aby przechwycić je do celów debugowania lub raportowania. Aby użyć własnego programu obsługi błędów, należy utworzyć funkcję, która ma sygnaturę **_purecall_handler** , a następnie użyć [_set_purecall_handler](get-purecall-handler-set-purecall-handler.md) , aby uczynić ją bieżącą obsługą.

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

## <a name="requirements"></a>Wymagania

Funkcja **_purecall** nie ma deklaracji nagłówka. **_Purecall_handler** typedef jest zdefiniowany w \<stdlib.h> .

## <a name="see-also"></a>Zobacz też

[Alfabetyczne zestawienie funkcji](crt-alphabetical-function-reference.md)<br/>
[_get_purecall_handler, _set_purecall_handler](get-purecall-handler-set-purecall-handler.md)<br/>

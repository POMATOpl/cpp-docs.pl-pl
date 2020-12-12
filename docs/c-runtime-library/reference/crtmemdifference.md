---
description: 'Dowiedz się więcej na temat: _CrtMemDifference'
title: _CrtMemDifference
ms.date: 11/04/2016
api_name:
- _CrtMemDifference
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
- ucrtbase.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _CrtMemDifference
- CrtMemDifference
helpviewer_keywords:
- CrtMemDifference function
- _CrtMemDifference function
ms.assetid: 0f327278-b551-482f-958b-76941f796ba4
ms.openlocfilehash: 076cead5f60df457171bbcdf2fd8690f0361870b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319654"
---
# <a name="_crtmemdifference"></a>_CrtMemDifference

Porównuje dwa stany pamięci i zwraca ich różnice (tylko wersja do debugowania).

## <a name="syntax"></a>Składnia

```C
int _CrtMemDifference(
   _CrtMemState *stateDiff,
   const _CrtMemState *oldState,
   const _CrtMemState *newState
);
```

### <a name="parameters"></a>Parametry

*stateDiff*<br/>
Wskaźnik do struktury **_CrtMemState** , który jest używany do przechowywania różnic między Stanami dwóch pamięci (zwrócone).

*oldState*<br/>
Wskaźnik do wcześniejszego stanu pamięci (struktura **_CrtMemState** ).

*newState*<br/>
Wskaźnik do późniejszego stanu pamięci (struktury **_CrtMemState** ).

## <a name="return-value"></a>Wartość zwracana

Jeśli Stany pamięci są znacznie różne, **_CrtMemDifference** zwraca wartość true. W przeciwnym razie funkcja zwraca wartość FALSE.

## <a name="remarks"></a>Uwagi

Funkcja **_CrtMemDifference** porównuje *oldState* i *NewState* i przechowuje różnice w *stateDiff*, które mogą następnie być używane przez aplikację w celu wykrywania przecieków pamięci i innych problemów z pamięcią. Gdy [_DEBUG](../../c-runtime-library/debug.md) nie jest zdefiniowany, wywołania do **_CrtMemDifference** są usuwane podczas przetwarzania wstępnego.

*NewState* i *oldState* muszą być prawidłowymi wskaźnikami do struktury **_CrtMemState** zdefiniowanej w CRTDBG. h, która została wprowadzona przez [_CrtMemCheckpoint](crtmemcheckpoint.md) przed wywołaniem **_CrtMemDifference**. *stateDiff* musi być wskaźnikiem do wcześniej przydzielonym wystąpieniem struktury **_CrtMemState** . Jeśli *stateDiff*, *NewState* lub *oldState* ma **wartość null**, zostanie wywołana procedura obsługi nieprawidłowego parametru, zgodnie z opisem w [walidacji parametru](../../c-runtime-library/parameter-validation.md). Jeśli wykonanie może być kontynuowane, [errno, _doserrno, _sys_errlist i _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) jest ustawiona na **EINVAL** , a funkcja zwraca wartość false.

**_CrtMemDifference** porównuje wartości pól **_CrtMemState** bloków w *oldState* z tymi w *NewState* i zapisuje wynik w *stateDiff*. Gdy liczba przyznanych typów bloków lub całkowita liczba przyznanych bloków dla każdego typu różni się między Stanami dwóch pamięci, Stany są uważane za znacząco różne. Różnica między największą ilością kiedykolwiek przydzieloną jednocześnie dla dwóch stanów, a różnica między całkowitą alokacją dla dwóch stanów jest również przechowywana w *stateDiff*.

Domyślnie wewnętrzne bloki uruchomieniowe C (**_CRT_BLOCK**) nie są uwzględnione w operacjach stanu pamięci. Funkcja [_CrtSetDbgFlag](crtsetdbgflag.md) może służyć do włączania **_CRTDBG_CHECK_CRT_DF** bitowej **_crtDbgFlag** w celu uwzględnienia tych bloków w przypadku wykrywania przecieków i innych operacji stanu pamięci. Zwolnione bloki pamięci (**_FREE_BLOCK**) nie powodują, że **_CrtMemDifference** zwracają wartość true.

Aby uzyskać więcej informacji o funkcjach stanu sterty i strukturze **_CrtMemState** , zobacz [funkcje raportowania stanu sterty](/visualstudio/debugger/crt-debug-heap-details). Aby uzyskać informacje o tym, jak bloki pamięci są przydzielane, inicjowane i zarządzane w wersji debugowania sterty podstawowej, zobacz [szczegóły sterty debugowania CRT](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|Opcjonalny nagłówek|
|-------------|---------------------|---------------------|
|**_CrtMemDifference**|\<crtdbg.h>|\<errno.h>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

**Biblioteki:** Debuguj tylko wersje [funkcji biblioteki CRT](../../c-runtime-library/crt-library-features.md) .

## <a name="see-also"></a>Zobacz też

[Procedury debugowania](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>

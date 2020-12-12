---
description: 'Dowiedz się więcej na temat: _set_abort_behavior'
title: _set_abort_behavior
ms.date: 4/2/2020
api_name:
- _set_abort_behavior
- _o__set_abort_behavior
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
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _set_abort_behavior
- set_abort_behavior
helpviewer_keywords:
- aborting programs
- _set_abort_behavior function
- set_abort_behavior function
ms.openlocfilehash: 1e024cf825115204f51e727d81af7aba74c305fb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97288909"
---
# <a name="_set_abort_behavior"></a>_set_abort_behavior

Określa akcję, która ma zostać podjęta w przypadku nienormalnego zakończenia programu.

> [!NOTE]
> Nie należy używać funkcji [Abort](abort.md) do zamykania aplikacji Microsoft Store, z wyjątkiem scenariuszy testowania lub debugowania. Sposób programistyczny lub interfejs użytkownika służący do zamykania aplikacji ze sklepu nie są dozwolone zgodnie z [zasadami Microsoft Storeymi](/legal/windows/agreements/store-policies). Aby uzyskać więcej informacji, zobacz [cykl życia aplikacji platformy UWP](/windows/uwp/launch-resume/app-lifecycle).

## <a name="syntax"></a>Składnia

```C
unsigned int _set_abort_behavior(
   unsigned int flags,
   unsigned int mask
);
```

### <a name="parameters"></a>Parametry

*znaczników*<br/>
Nowa wartość flag [przerwania](abort.md) .

*maska*<br/>
Maska dla bitów flag [przerwania](abort.md) do ustawienia.

## <a name="return-value"></a>Wartość zwracana

Stara wartość flag.

## <a name="remarks"></a>Uwagi

Istnieją dwie flagi [przerwania](abort.md) : **_WRITE_ABORT_MSG** i **_CALL_REPORTFAULT**. **_WRITE_ABORT_MSG** określa, czy przydatna wiadomość tekstowa jest drukowana, gdy program jest nienormalnie zakończony. Komunikat określa, że aplikacja wywołuje funkcję [Abort](abort.md) . Domyślnym zachowaniem jest drukowanie wiadomości. **_CALL_REPORTFAULT**, jeśli ustawiona, określa, że zrzut awaryjny programu Watson jest generowany i raportowany po wywołaniu metody [Abort](abort.md) . Domyślnie Raportowanie zrzutów awaryjnych jest włączone w kompilacjach, które nie są DEBUGOWANe.

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_set_abort_behavior**|\<stdlib.h>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Przykład

```C
// crt_set_abort_behavior.c
// compile with: /TC
#include <stdlib.h>

int main()
{
   printf("Suppressing the abort message. If successful, this message"
          " will be the only output.\n");
   // Suppress the abort message
   _set_abort_behavior( 0, _WRITE_ABORT_MSG);
   abort();
}
```

```Output
Suppressing the abort message. If successful, this message will be the only output.
```

## <a name="see-also"></a>Zobacz także

[przerwij](abort.md)<br/>

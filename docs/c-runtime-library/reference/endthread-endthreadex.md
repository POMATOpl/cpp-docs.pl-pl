---
description: 'Dowiedz się więcej na temat: _endthread, _endthreadex'
title: _endthread, _endthreadex
ms.date: 4/2/2020
api_name:
- _endthread
- _endthreadex
- _o__endthread
- _o__endthreadex
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
- _endthread
- endthreadex
- _endthreadex
- endthread
helpviewer_keywords:
- _endthread function
- endthread function
- terminating threads
- endthreadex function
- _endthreadex function
- threading [C++], terminating threads
ms.assetid: 18a91f2f-659e-40b4-b266-ec12dcf2abf5
ms.openlocfilehash: ef74cac4cbe23a021ed8d796f92f2767695eb08e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332835"
---
# <a name="_endthread-_endthreadex"></a>_endthread, _endthreadex

Kończy wątek; **_endthread** przerywa wątek tworzony przez **_beginthread** i  **_endthreadex** kończy wątek tworzony przez **_beginthreadex**.

## <a name="syntax"></a>Składnia

```C
void _endthread( void );
void _endthreadex(
   unsigned retval
);
```

### <a name="parameters"></a>Parametry

*retval*<br/>
Kod zakończenia wątku.

## <a name="remarks"></a>Uwagi

Możesz wywołać **_endthread** lub **_endthreadex** jawnie, aby zakończyć wątek. Jednakże **_endthread** lub **_endthreadex** jest wywoływana automatycznie, gdy wątek zwraca z procedury przekazywanej jako parametr do **_beginthread** lub **_beginthreadex**. Zakończenie wątku z wywołaniem **endthread** lub **_endthreadex** pomaga zapewnić poprawne odzyskiwanie zasobów przyznanych dla wątku.

> [!NOTE]
> Dla pliku wykonywalnego połączonego z libcmt. lib nie wywołuj interfejsu API Win32 [ExitThread —](/windows/win32/api/processthreadsapi/nf-processthreadsapi-exitthread) ; Zapobiega to odzyskiwaniu przyznanych zasobów przez system czasu wykonywania. **_endthread** i **_endthreadex** odzyskiwanie przydzieloną zasobów wątków, a następnie Wywołaj **ExitThread —**.

**_endthread** automatycznie zamyka dojście wątku. (To zachowanie różni się od interfejsu API Win32 **ExitThread —** ). W związku z tym, gdy używasz **_beginthread** i **_endthread**, nie zamykaj jawnie uchwytu wątku, wywołując interfejs API [CloseHandle](/windows/win32/api/handleapi/nf-handleapi-closehandle) Win32.

Podobnie jak w przypadku interfejsu API Win32 **ExitThread —** , **_endthreadex** nie zamyka dojścia wątku. W związku z tym, jeśli używasz **_beginthreadex** i **_endthreadex**, musisz zamknąć uchwyt wątku, wywołując interfejs API **CloseHandle** Win32.

> [!NOTE]
> **_endthread** i **_endthreadex** powodują, że destruktory języka C++ oczekujące w wątku nie zostaną wywołane.

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

## <a name="requirements"></a>Wymagania

|Funkcja|Wymagany nagłówek|
|--------------|---------------------|
|**_endthread**|\<process.h>|
|**_endthreadex**|\<process.h>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Biblioteki

Wielowątkowe wersje [bibliotek uruchomieniowych języka C](../../c-runtime-library/crt-library-features.md) .

## <a name="example"></a>Przykład

Zapoznaj się z przykładem [_beginthread](beginthread-beginthreadex.md).

## <a name="see-also"></a>Zobacz też

[Proces i kontrola środowiska](../../c-runtime-library/process-and-environment-control.md)<br/>
[_beginthread, _beginthreadex](beginthread-beginthreadex.md)<br/>

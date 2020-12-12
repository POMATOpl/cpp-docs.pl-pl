---
description: 'Dowiedz się więcej na temat: _CrtSetDumpClient'
title: _CrtSetDumpClient
ms.date: 11/04/2016
api_name:
- _CrtSetDumpClient
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
- _CrtSetDumpClient
- CrtSetDumpClient
helpviewer_keywords:
- _CrtSetDumpClient function
- CrtSetDumpClient function
ms.assetid: f3dd06d0-c331-4a12-b68d-25378d112033
ms.openlocfilehash: 89a2648aae62fc7f62b04519eacce4e0f67002f1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319537"
---
# <a name="_crtsetdumpclient"></a>_CrtSetDumpClient

Instaluje funkcję zdefiniowaną przez aplikację w celu zrzutu bloków pamięci typu **_CLIENT_BLOCK** (tylko wersja do debugowania).

## <a name="syntax"></a>Składnia

```C
_CRT_DUMP_CLIENT _CrtSetDumpClient( _CRT_DUMP_CLIENT dumpClient );
```

### <a name="parameters"></a>Parametry

*dumpClient*<br/>
Nowa funkcja zrzutów pamięci zdefiniowana przez klienta do podłączania do procesu zrzutu pamięci debugowania w czasie wykonywania języka C.

## <a name="return-value"></a>Wartość zwracana

Zwraca wcześniej zdefiniowaną funkcję zrzutu bloku klienta.

## <a name="remarks"></a>Uwagi

Funkcja **_CrtSetDumpClient** umożliwia aplikacji podpiąć własną funkcję w celu zrzutów obiektów przechowywanych w blokach pamięci **_CLIENT_BLOCK** do procesu zrzutu pamięci debugowania w czasie wykonywania C. W związku z tym za każdym razem, gdy funkcja zrzutu debugowania, taka jak [_CrtMemDumpAllObjectsSince](crtmemdumpallobjectssince.md) lub [_CrtDumpMemoryLeaks](crtdumpmemoryleaks.md) zrzuca blok pamięci **_CLIENT_BLOCK** , wywoływana jest również funkcja zrzutu aplikacji. **_CrtSetDumpClient** zapewnia aplikacji prostą metodę wykrywania przecieków pamięci i sprawdzania poprawności zawartości danych przechowywanych w blokach **_CLIENT_BLOCK** . Gdy [_DEBUG](../../c-runtime-library/debug.md) nie jest zdefiniowany, wywołania do **_CrtSetDumpClient** są usuwane podczas przetwarzania wstępnego.

Funkcja **_CrtSetDumpClient** instaluje nową funkcję zrzutu zdefiniowaną przez aplikację określoną w *dumpClient* i zwraca wcześniej zdefiniowaną funkcję zrzutu. Przykładem funkcji zrzutu bloku klienta jest następująca:

```C
void DumpClientFunction( void *userPortion, size_t blockSize );
```

Argument *userPortion* jest wskaźnikiem do początku części danych użytkownika bloku pamięci i *rozmiar bloku* określa rozmiar przydzielony blok pamięci w bajtach. Funkcja zrzutu bloku klienta musi zwracać **`void`** . Wskaźnik do funkcji zrzutu klienta, która jest przenoszona do **_CrtSetDumpClient** jest typu **_CRT_DUMP_CLIENT**, zgodnie z definicją w CRTDBG. h:

```C
typedef void (__cdecl *_CRT_DUMP_CLIENT)( void *, size_t );
```

Aby uzyskać więcej informacji na temat funkcji, które działają na blokach pamięci typu **_CLIENT_BLOCK** , zobacz [funkcje punktu zaczepienia bloku klienta](/visualstudio/debugger/client-block-hook-functions). Funkcja [_CrtReportBlockType](crtreportblocktype.md) może służyć do zwracania informacji o typach bloków i podtypach.

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_CrtSetDumpClient**|\<crtdbg.h>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Biblioteki

Debuguj wersje wyłącznie [bibliotek uruchomieniowych C](../../c-runtime-library/crt-library-features.md) .

## <a name="see-also"></a>Zobacz też

[Procedury debugowania](../../c-runtime-library/debug-routines.md)<br/>
[_CrtReportBlockType](crtreportblocktype.md)<br/>
[_CrtGetDumpClient](crtgetdumpclient.md)<br/>

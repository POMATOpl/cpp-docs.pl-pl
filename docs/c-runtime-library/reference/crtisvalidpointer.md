---
description: 'Dowiedz się więcej na temat: _CrtIsValidPointer'
title: _CrtIsValidPointer
ms.date: 11/04/2016
api_name:
- _CrtIsValidPointer
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
- CrtlsValidPointer
- _CrtIsValidPointer
helpviewer_keywords:
- CrtIsValidPointer function
- _CrtIsValidPointer function
ms.assetid: 91c35590-ea5e-450f-a15d-ad8d62ade1fa
ms.openlocfilehash: 0bc0c3f9cf3ab581a145c626abee5641cf6bd550
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319693"
---
# <a name="_crtisvalidpointer"></a>_CrtIsValidPointer

Sprawdza, czy wskaźnik nie ma wartości null. W wersjach biblioteki wykonawczej C przed programem Visual Studio 2010 sprawdza, czy określony zakres pamięci jest prawidłowy do odczytu i zapisu (tylko wersja do debugowania).

## <a name="syntax"></a>Składnia

```C
int _CrtIsValidPointer(
   const void *address,
   unsigned int size,
   int access
);
```

### <a name="parameters"></a>Parametry

*Ulica*<br/>
Wskazuje początek zakresu pamięci, aby sprawdzić poprawność.

*zmienia*<br/>
Rozmiar określonego zakresu pamięci (w bajtach).

*niego*<br/>
Ułatwienia dostępu do odczytu i zapisu w celu określenia zakresu pamięci.

## <a name="return-value"></a>Wartość zwracana

**_CrtIsValidPointer** zwraca wartość true, jeśli określony wskaźnik nie ma wartości null. W wersjach biblioteki CRT przed Visual Studio 2010 zwraca wartość TRUE, jeśli zakres pamięci jest prawidłowy dla określonej operacji lub operacji. W przeciwnym razie funkcja zwraca wartość FALSE.

## <a name="remarks"></a>Uwagi

Począwszy od biblioteki CRT w programie Visual Studio 2010, parametry *rozmiaru* i *dostępu* są ignorowane, a **_CrtIsValidPointer** sprawdza tylko, czy określony *adres* nie ma wartości null. Ponieważ ten test jest łatwy do wykonania, nie zalecamy korzystania z tej funkcji. W wersjach przed Visual Studio 2010 funkcja sprawdza, czy zakres pamięci rozpoczynający się pod *adresem* i rozszerzanie *rozmiaru* bajtów jest prawidłowy dla określonej operacji lub operacji dostępności. Gdy *dostęp* jest ustawiony na wartość true, zakres pamięci jest weryfikowany zarówno do odczytu, jak i do zapisu. Gdy *dostęp* ma wartość false, zakres pamięci jest weryfikowany tylko do odczytu. Gdy [_DEBUG](../../c-runtime-library/debug.md) nie jest zdefiniowany, wywołania do **_CrtIsValidPointer** są usuwane podczas przetwarzania wstępnego.

Ponieważ ta funkcja zwraca wartość TRUE lub FALSE, można ją przesłać do jednego z [_ASSERTych](assert-asserte-assert-expr-macros.md) makr, aby utworzyć prosty mechanizm obsługi błędów debugowania. Poniższy przykład powoduje niepowodzenie potwierdzenia, jeśli zakres pamięci nie jest prawidłowy dla operacji odczytu i zapisu:

```C
_ASSERTE( _CrtIsValidPointer( address, size, TRUE ) );
```

Aby uzyskać więcej informacji o tym, jak **_CrtIsValidPointer** mogą być używane z innymi funkcjami i makrami debugowania, zobacz [makra na potrzeby raportowania](/visualstudio/debugger/macros-for-reporting). Aby uzyskać informacje o tym, jak bloki pamięci są przydzielane, inicjowane i zarządzane w wersji debugowania sterty podstawowej, zobacz [szczegóły sterty debugowania CRT](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_CrtIsValidPointer**|\<crtdbg.h>|

**_CrtIsValidPointer** to rozszerzenie firmy Microsoft. Aby uzyskać informacje o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Biblioteki

Debuguj wersje wyłącznie [bibliotek uruchomieniowych C](../../c-runtime-library/crt-library-features.md) .

## <a name="example"></a>Przykład

Zobacz przykład tematu [_CrtIsValidHeapPointer](crtisvalidheappointer.md) .

## <a name="see-also"></a>Zobacz też

[Procedury debugowania](../../c-runtime-library/debug-routines.md)<br/>

---
description: 'Dowiedz się więcej o: makro makro OffsetOf'
title: makro OffsetOf — makro
ms.date: 11/04/2016
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
- offsetof
helpviewer_keywords:
- structure members, offset
- offsetof macro
ms.assetid: f3b4eb16-a882-4d38-afc9-eebd976a7352
ms.openlocfilehash: 055bda67bae178143561acd91b517c431f77cac0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97256272"
---
# <a name="offsetof-macro"></a>makro OffsetOf — makro

Pobiera przesunięcie elementu członkowskiego od początku jego struktury nadrzędnej.

## <a name="syntax"></a>Składnia

```C
size_t offsetof(
   structName,
   memberName
);
```

### <a name="parameters"></a>Parametry

*Typ struktury*<br/>
Nazwa nadrzędnej struktury danych.

*memberName*<br/>
Nazwa elementu członkowskiego w nadrzędnej strukturze danych, dla którego ma zostać określone przesunięcie.

## <a name="return-value"></a>Wartość zwracana

**makro OffsetOf** zwraca przesunięcie w bajtach określonego elementu członkowskiego od początku jego nadrzędnej struktury danych. Nie jest on zdefiniowany dla pól bitowych.

## <a name="remarks"></a>Uwagi

Makro **makro OffsetOf** zwraca przesunięcie w bajtach *elementu MemberName* od początku struktury określonej przez *structname* jako wartość typu **size_t**. Możesz określić typy za pomocą **`struct`** słowa kluczowego.

> [!NOTE]
> **makro OffsetOf** nie jest funkcją i nie można jej opisać przy użyciu prototypu języka C.

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**makro OffsetOf**|\<stddef.h>|

Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Biblioteki

Wszystkie wersje [bibliotek uruchomieniowych języka C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Zobacz też

[Alokacja pamięci](../../c-runtime-library/memory-allocation.md)<br/>

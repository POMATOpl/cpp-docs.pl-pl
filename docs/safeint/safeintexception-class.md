---
description: 'Dowiedz się więcej na temat: Klasa SafeIntException'
title: SafeIntException — Klasa
ms.date: 10/22/2018
ms.topic: reference
f1_keywords:
- SafeIntException Class
- SafeIntException
- SafeIntException.SafeIntException
- SafeIntException::SafeIntException
helpviewer_keywords:
- SafeIntException class
- SafeIntException, constructor
ms.assetid: 88bef958-1f48-4d55-ad4f-d1f9581a293a
ms.openlocfilehash: 6a7be21b0dfa42a23ba60eac7eb3f4ebbf1629ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149581"
---
# <a name="safeintexception-class"></a>SafeIntException — Klasa

`SafeInt`Klasa używa `SafeIntException` do identyfikowania dlaczego nie można ukończyć operacji matematycznej.

> [!NOTE]
> Najnowsza wersja tej biblioteki znajduje się w lokalizacji [https://github.com/dcleblanc/SafeInt](https://github.com/dcleblanc/SafeInt) .

## <a name="syntax"></a>Składnia

```cpp
class SafeIntException;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

Nazwa                                                    | Opis
------------------------------------------------------- | ------------------------------------
[SafeIntException::SafeIntException](#safeintexception) | Tworzy obiekt `SafeIntException`.

## <a name="remarks"></a>Uwagi

[Klasa SafeInt](safeint-class.md) jest jedyną klasą, która używa `SafeIntException` klasy.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`SafeIntException`

## <a name="requirements"></a>Wymagania

**Nagłówek:** SafeInt. h

**Przestrzeń nazw:** MSL:: Utilities

## <a name="safeintexceptionsafeintexception"></a><a name="safeintexception"></a> SafeIntException:: SafeIntException

Tworzy obiekt `SafeIntException`.

```cpp
SafeIntException();

SafeIntException(
   SafeIntError code
);
```

### <a name="parameters"></a>Parametry

*kodu*<br/>
podczas Wyliczana wartość danych opisująca błąd, który wystąpił.

### <a name="remarks"></a>Uwagi

Możliwe wartości *kodu* są zdefiniowane w pliku SafeInt. h. Dla wygody można również wymienić wartości w tym miejscu.

- `SafeIntNoError`
- `SafeIntArithmeticOverflow`
- `SafeIntDivideByZero`

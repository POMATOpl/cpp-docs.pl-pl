---
description: 'Dowiedz się więcej o: operatory ATL'
title: Operatory ATL
ms.date: 11/04/2016
helpviewer_keywords:
- operators [ATL]
ms.assetid: 58ccd252-2869-45ee-8a5c-3ca40ee7f8a2
ms.openlocfilehash: 8c336732aeee9146b89e300580c0fbee506ec343
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158689"
---
# <a name="atl-operators"></a>Operatory ATL

Ta sekcja zawiera tematy referencyjne dla operatorów globalnych ATL.

|Operator|Opis|
|--------------|-----------------|
|[operator = =](#operator_eq_eq)|Porównuje dwa `CSid` obiekty lub `SID` struktury pod kątem równości.|
|[operator! =](#operator_neq)|Porównuje dwa `CSid` obiekty lub `SID` struktury pod kątem nierówności.|
|[<operatora ](#operator_lt)|Testuje, czy `CSid` obiekt lub `SID` Struktura po lewej stronie operatora jest mniejsza niż `CSid` obiekt lub `SID` Struktura po prawej stronie (na potrzeby zgodności biblioteki standardowej języka C++).|
|[>operatora ](#operator_gt)|Testuje, czy `CSid` obiekt lub `SID` Struktura po lewej stronie operatora są większe niż `CSid` obiekt lub `SID` Struktura po prawej stronie (w przypadku zgodności biblioteki standardowej języka C++).|
|[<operatora =](#operator_lt__eq)|Testuje, czy `CSid` obiekt lub `SID` Struktura po lewej stronie operatora jest mniejsza lub równa `CSid` obiektowi lub `SID` strukturze po prawej stronie (w przypadku zgodności biblioteki standardowej języka C++).|
|[>operatora =](#operator_gt__eq)|Testuje, czy `CSid` obiekt lub `SID` Struktura po lewej stronie operatora jest większa lub równa `CSid` obiektowi lub `SID` strukturze po prawej stronie (w przypadku zgodności biblioteki standardowej języka C++).|

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlsecurity. h.

## <a name="operator-"></a><a name="operator_eq_eq"></a> operator = =

Porównuje `CSid` obiekty lub `SID` (identyfikator zabezpieczeń) struktur dla równości.

```cpp
bool operator==(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametry

*LHS*<br/>
Pierwszy `CSid` obiekt lub `SID` Struktura do porównania.

*RHS*<br/>
Drugi `CSid` obiekt lub `SID` Struktura do porównania.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE, jeśli obiekty są równe, FAŁSZ, jeśli nie są równe.

## <a name="operator-"></a><a name="operator_neq"></a> operator! =

Porównuje `CSid` obiekty lub `SID` (identyfikator zabezpieczeń) struktur dla nierówności.

```cpp
bool operator==(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametry

*LHS*<br/>
Pierwszy `CSid` obiekt lub `SID` Struktura do porównania.

*RHS*<br/>
Drugi `CSid` obiekt lub `SID` Struktura do porównania.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE, jeśli obiekty nie są równe, FAŁSZ, jeśli są równe.

## <a name="operator-"></a><a name="operator_lt"></a> < operatora

Testuje, czy `CSid` obiekt lub `SID` Struktura po lewej stronie operatora jest mniejsza niż `CSid` obiekt lub `SID` Struktura po prawej stronie (na potrzeby zgodności biblioteki standardowej języka C++).

```cpp
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametry

*LHS*<br/>
Pierwszy `CSid` obiekt lub `SID` Struktura do porównania.

*RHS*<br/>
Drugi `CSid` obiekt lub `SID` Struktura do porównania.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE, jeśli adres obiektu *LHS* jest mniejszy niż adres obiektu *RHS* , w przeciwnym razie false.

### <a name="remarks"></a>Uwagi

Ten operator działa na adresie `CSid` obiektu lub `SID` struktury i jest zaimplementowany w celu zapewnienia zgodności z klasami kolekcji biblioteki standardowej języka C++.

## <a name="operator-"></a><a name="operator_gt"></a> > operatora

Testuje, czy `CSid` obiekt lub `SID` Struktura po lewej stronie operatora są większe niż `CSid` obiekt lub `SID` Struktura po prawej stronie (w przypadku zgodności biblioteki standardowej języka C++).

```cpp
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametry

*LHS*<br/>
Pierwszy `CSid` obiekt lub `SID` Struktura do porównania.

*RHS*<br/>
Drugi `CSid` obiekt lub `SID` Struktura do porównania.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE, jeśli adres *LHS* jest większy niż adres *RHS*, w przeciwnym razie false.

### <a name="remarks"></a>Uwagi

Ten operator działa na adresie `CSid` obiektu lub `SID` struktury i jest zaimplementowany w celu zapewnienia zgodności z klasami kolekcji biblioteki standardowej języka C++.

## <a name="operator-"></a><a name="operator_lt__eq"></a> <operatora =

Testuje, czy `CSid` obiekt lub `SID` Struktura po lewej stronie operatora jest mniejsza lub równa `CSid` obiektowi lub `SID` strukturze po prawej stronie (w przypadku zgodności biblioteki standardowej języka C++).

```cpp
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametry

*LHS*<br/>
Pierwszy `CSid` obiekt lub `SID` Struktura do porównania.

*RHS*<br/>
Drugi `CSid` obiekt lub `SID` Struktura do porównania.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE, jeśli adres *LHS* jest mniejszy lub równy adresowi *RHS*, w przeciwnym razie false.

### <a name="remarks"></a>Uwagi

Ten operator działa na adresie `CSid` obiektu lub `SID` struktury i jest zaimplementowany w celu zapewnienia zgodności z klasami kolekcji biblioteki standardowej języka C++.

## <a name="operator-"></a><a name="operator_gt__eq"></a> >operatora =

Testuje, czy `CSid` obiekt lub `SID` Struktura po lewej stronie operatora jest większa lub równa `CSid` obiektowi lub `SID` strukturze po prawej stronie (w przypadku zgodności biblioteki standardowej języka C++).

```cpp
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametry

*LHS*<br/>
Pierwszy `CSid` obiekt lub `SID` Struktura do porównania.

*RHS*<br/>
Drugi `CSid` obiekt lub `SID` Struktura do porównania.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE, jeśli adres *LHS* jest większy lub równy adresowi *RHS*, w przeciwnym razie false.

### <a name="remarks"></a>Uwagi

Ten operator działa na adresie `CSid` obiektu lub `SID` struktury i jest zaimplementowany w celu zapewnienia zgodności z klasami kolekcji biblioteki standardowej języka C++.

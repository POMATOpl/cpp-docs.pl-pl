---
description: Dowiedz się więcej na temat klasy cancellation_token_registration
title: cancellation_token_registration — Klasa
ms.date: 11/04/2016
f1_keywords:
- cancellation_token_registration
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_registration
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_registration::cancellation_token_registration
helpviewer_keywords:
- cancellation_token_registration class
ms.assetid: 823d63f4-7233-4d65-8976-6152ccf12d0e
ms.openlocfilehash: 1901e5132a9bad6849b1b00a6be63caf9afc9170
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172144"
---
# <a name="cancellation_token_registration-class"></a>cancellation_token_registration — Klasa

`cancellation_token_registration`Klasa reprezentuje powiadomienie wywołania zwrotnego z `cancellation_token` . Gdy `register` Metoda w `cancellation_token` jest używana do otrzymywania powiadomień o wystąpieniu anulowania, `cancellation_token_registration` obiekt jest zwracany jako dojście do wywołania zwrotnego, aby obiekt wywołujący mógł zażądać określonego wywołania zwrotnego za pomocą `deregister` metody.

## <a name="syntax"></a>Składnia

```cpp
class cancellation_token_registration;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[cancellation_token_registration](#ctor)||
|[~ cancellation_token_registration destruktor](#dtor)||

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[operator! =](#operator_neq)||
|[operator =](#operator_eq)||
|[operator = =](#operator_eq_eq)||

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`cancellation_token_registration`

## <a name="requirements"></a>Wymagania

**Nagłówek:** pplcancellation_token. h

**Przestrzeń nazw:** współbieżność

## <a name="cancellation_token_registration"></a><a name="dtor"></a> ~ cancellation_token_registration

```cpp
~cancellation_token_registration();
```

## <a name="cancellation_token_registration"></a><a name="ctor"></a> cancellation_token_registration

```cpp
cancellation_token_registration();

cancellation_token_registration(const cancellation_token_registration& _Src);

cancellation_token_registration(cancellation_token_registration&& _Src);
```

### <a name="parameters"></a>Parametry

*_Src*<br/>
`cancellation_token_registration`Do kopiowania lub przenoszenia.

## <a name="operator"></a><a name="operator_neq"></a> operator! =

```cpp
bool operator!= (const cancellation_token_registration& _Rhs) const;
```

### <a name="parameters"></a>Parametry

*_Rhs*<br/>
`cancellation_token_registration`Do porównania.

### <a name="return-value"></a>Wartość zwracana

## <a name="operator"></a><a name="operator_eq"></a> operator =

```cpp
cancellation_token_registration& operator= (const cancellation_token_registration& _Src);

cancellation_token_registration& operator= (cancellation_token_registration&& _Src);
```

### <a name="parameters"></a>Parametry

*_Src*<br/>
`cancellation_token_registration`Do przypisania.

### <a name="return-value"></a>Wartość zwracana

## <a name="operator"></a><a name="operator_eq_eq"></a> operator = =

```cpp
bool operator== (const cancellation_token_registration& _Rhs) const;
```

### <a name="parameters"></a>Parametry

*_Rhs*<br/>
`cancellation_token_registration`Do porównania.

### <a name="return-value"></a>Wartość zwracana

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)

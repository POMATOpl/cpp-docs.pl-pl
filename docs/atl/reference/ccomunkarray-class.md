---
description: 'Dowiedz się więcej na temat: Klasa CComUnkArray'
title: Klasa CComUnkArray
ms.date: 11/04/2016
f1_keywords:
- CComUnkArray
- ATLCOM/ATL::CComUnkArray
- ATLCOM/ATL::CComUnkArray::CComUnkArray
- ATLCOM/ATL::CComUnkArray::Add
- ATLCOM/ATL::CComUnkArray::begin
- ATLCOM/ATL::CComUnkArray::end
- ATLCOM/ATL::CComUnkArray::GetCookie
- ATLCOM/ATL::CComUnkArray::GetUnknown
- ATLCOM/ATL::CComUnkArray::Remove
helpviewer_keywords:
- connection points [C++], managing
- CComUnkArray class
ms.assetid: 5fd4b378-a7b5-4cc1-8866-8ab72a73639e
ms.openlocfilehash: e03022fb751b487debb9f81d9e3d99ce46f1b9e7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142145"
---
# <a name="ccomunkarray-class"></a>Klasa CComUnkArray

Ta klasa przechowuje `IUnknown` wskaźniki i jest przeznaczona do użycia jako parametr klasy szablonu [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) .

## <a name="syntax"></a>Składnia

```
template<unsigned int nMaxSize>
class CComUnkArray
```

#### <a name="parameters"></a>Parametry

*nMaxSize*<br/>
Maksymalna liczba `IUnknown` wskaźników, które mogą być przechowywane w tablicy statycznej.

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CComUnkArray::CComUnkArray](#ccomunkarray)|Konstruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CComUnkArray:: Add](#add)|Wywołaj tę metodę, aby dodać `IUnknown` wskaźnik do tablicy.|
|[CComUnkArray:: BEGIN](#begin)|Zwraca wskaźnik do pierwszego `IUnknown` wskaźnika w kolekcji.|
|[CComUnkArray:: end](#end)|Zwraca wskaźnik do jednego z nich poza ostatnim `IUnknown` wskaźnikiem w kolekcji.|
|[CComUnkArray:: getcookas](#getcookie)|Wywołaj tę metodę, aby pobrać plik cookie skojarzony z danym `IUnknown` wskaźnikiem.|
|[CComUnkArray:: getnieznany](#getunknown)|Wywołaj tę metodę, aby uzyskać `IUnknown` wskaźnik skojarzony z danym plikiem cookie.|
|[CComUnkArray:: Remove](#remove)|Wywołaj tę metodę, aby usunąć `IUnknown` wskaźnik z tablicy.|

## <a name="remarks"></a>Uwagi

`CComUnkArray` zawiera stałą liczbę `IUnknown` wskaźników, każdy interfejs w punkcie połączenia. `CComUnkArray` może być używany jako parametr klasy szablonu [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) . `CComUnkArray<1>` jest specjalizacją szablonu `CComUnkArray` , która została zoptymalizowana pod kątem jednego punktu połączenia.

`CComUnkArray`Metody [BEGIN](#begin) i [End](#end) mogą służyć do zapętlenia przez wszystkie punkty połączenia (na przykład gdy zdarzenie jest wyzwalane).

Aby uzyskać szczegółowe informacje na temat automatyzacji tworzenia serwerów proxy punktu połączenia [, zobacz Dodawanie punktów połączenia do obiektu](../../atl/adding-connection-points-to-an-object.md) .

> [!NOTE]
> **Uwaga** Klasa [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md) jest używana przez kreatora **dodawania klasy** podczas tworzenia kontrolki, która ma punkty połączenia. Jeśli chcesz ręcznie określić liczbę punktów połączenia, Zmień odwołanie z `CComDynamicUnkArray` do `CComUnkArray<` *n* `>` , gdzie *n* to liczba wymaganych punktów połączenia.

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcom. h

## <a name="ccomunkarrayadd"></a><a name="add"></a> CComUnkArray:: Add

Wywołaj tę metodę, aby dodać `IUnknown` wskaźnik do tablicy.

```
DWORD Add(IUnknown* pUnk);
```

### <a name="parameters"></a>Parametry

*Punkt*<br/>
Wywołaj tę metodę, aby dodać `IUnknown` wskaźnik do tablicy.

### <a name="return-value"></a>Wartość zwracana

Zwraca plik cookie skojarzony z nowo dodanym wskaźnikiem lub 0, jeśli tablica nie jest wystarczająco duża, aby można było zawierać nowy wskaźnik.

## <a name="ccomunkarraybegin"></a><a name="begin"></a> CComUnkArray:: BEGIN

Zwraca wskaźnik do początku kolekcji `IUnknown` wskaźników interfejsu.

```
IUnknown**
    begin();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do `IUnknown` wskaźnika interfejsu.

### <a name="remarks"></a>Uwagi

Kolekcja zawiera wskaźniki do interfejsów przechowywanych lokalnie jako `IUnknown` . Każdy interfejs jest rzutowany `IUnknown` do rzeczywistego typu interfejsu, a następnie wywoływany przez niego. Nie trzeba najpierw wykonywać zapytania dotyczącego interfejsu.

Przed użyciem `IUnknown` interfejsu należy sprawdzić, czy nie jest on pusty.

## <a name="ccomunkarrayccomunkarray"></a><a name="ccomunkarray"></a> CComUnkArray::CComUnkArray

Konstruktor.

```
CComUnkArray();
```

### <a name="remarks"></a>Uwagi

Ustawia kolekcję do przechowywania `nMaxSize` `IUnknown` wskaźników i inicjuje wskaźniki do wartości null.

## <a name="ccomunkarrayend"></a><a name="end"></a> CComUnkArray:: end

Zwraca wskaźnik do jednego z nich poza ostatnim `IUnknown` wskaźnikiem w kolekcji.

```
IUnknown**
    end();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do `IUnknown` wskaźnika interfejsu.

### <a name="remarks"></a>Uwagi

`CComUnkArray`Metody `begin` i `end` mogą być używane do zapętlenia przez wszystkie punkty połączenia, na przykład gdy zdarzenie jest wyzwalane.

[!code-cpp[NVC_ATL_COM#44](../../atl/codesnippet/cpp/ccomunkarray-class_1.cpp)]

## <a name="ccomunkarraygetcookie"></a><a name="getcookie"></a> CComUnkArray:: getcookas

Wywołaj tę metodę, aby pobrać plik cookie skojarzony z danym `IUnknown` wskaźnikiem.

```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```

### <a name="parameters"></a>Parametry

*ppFind*<br/>
`IUnknown`Wskaźnik, dla którego wymagany jest skojarzony plik cookie.

### <a name="return-value"></a>Wartość zwracana

Zwraca plik cookie skojarzony ze `IUnknown` wskaźnikiem lub 0, jeśli nie znaleziono zgodnego `IUnknown` wskaźnika.

### <a name="remarks"></a>Uwagi

Jeśli istnieje więcej niż jedno wystąpienie tego samego `IUnknown` wskaźnika, funkcja ta zwraca plik cookie dla pierwszej z nich.

## <a name="ccomunkarraygetunknown"></a><a name="getunknown"></a> CComUnkArray:: getnieznany

Wywołaj tę metodę, aby uzyskać `IUnknown` wskaźnik skojarzony z danym plikiem cookie.

```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```

### <a name="parameters"></a>Parametry

*dwCookie*<br/>
Plik cookie, dla którego `IUnknown` wymagany jest skojarzony wskaźnik.

### <a name="return-value"></a>Wartość zwracana

Zwraca `IUnknown` wskaźnik lub wartość null, jeśli nie zostanie znaleziony pasujący plik cookie.

## <a name="ccomunkarrayremove"></a><a name="remove"></a> CComUnkArray:: Remove

Wywołaj tę metodę, aby usunąć `IUnknown` wskaźnik z tablicy.

```
BOOL Remove(DWORD dwCookie);
```

### <a name="parameters"></a>Parametry

*dwCookie*<br/>
Plik cookie odwołujący się `IUnknown` do wskaźnika, który ma zostać usunięty z tablicy.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE, jeśli wskaźnik jest usuwany, w przeciwnym razie FALSE.

## <a name="see-also"></a>Zobacz też

[Klasa CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)

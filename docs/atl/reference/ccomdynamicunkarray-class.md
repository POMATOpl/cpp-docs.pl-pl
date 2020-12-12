---
description: 'Dowiedz się więcej na temat: Klasa CComDynamicUnkArray'
title: Klasa CComDynamicUnkArray
ms.date: 11/04/2016
f1_keywords:
- CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray::CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray::Add
- ATLCOM/ATL::CComDynamicUnkArray::begin
- ATLCOM/ATL::CComDynamicUnkArray::clear
- ATLCOM/ATL::CComDynamicUnkArray::end
- ATLCOM/ATL::CComDynamicUnkArray::GetAt
- ATLCOM/ATL::CComDynamicUnkArray::GetCookie
- ATLCOM/ATL::CComDynamicUnkArray::GetSize
- ATLCOM/ATL::CComDynamicUnkArray::GetUnknown
- ATLCOM/ATL::CComDynamicUnkArray::Remove
helpviewer_keywords:
- connection points [C++], managing
- CComDynamicUnkArray class
ms.assetid: 202470d7-9a1b-498f-b96d-659d681acd65
ms.openlocfilehash: fe817b097bbb75c7d09bffdb6883e5ac4a76f966
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152090"
---
# <a name="ccomdynamicunkarray-class"></a>Klasa CComDynamicUnkArray

Ta klasa przechowuje tablicę `IUnknown` wskaźników.

## <a name="syntax"></a>Składnia

```
class CComDynamicUnkArray
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CComDynamicUnkArray::CComDynamicUnkArray](#ccomdynamicunkarray)|Konstruktor. Inicjuje wartości kolekcji na wartość NULL, a rozmiar kolekcji to zero.|
|[CComDynamicUnkArray:: ~ CComDynamicUnkArray](#dtor)|Destruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CComDynamicUnkArray:: Add](#add)|Wywołaj tę metodę, aby dodać `IUnknown` wskaźnik do tablicy.|
|[CComDynamicUnkArray:: BEGIN](#begin)|Zwraca wskaźnik do pierwszego `IUnknown` wskaźnika w kolekcji.|
|[CComDynamicUnkArray:: Clear](#clear)|Opróżnia tablicę.|
|[CComDynamicUnkArray:: end](#end)|Zwraca wskaźnik do jednego z nich poza ostatnim `IUnknown` wskaźnikiem w kolekcji.|
|[CComDynamicUnkArray::GetAt](#getat)|Pobiera element pod określonym indeksem.|
|[CComDynamicUnkArray:: getcookas](#getcookie)|Wywołaj tę metodę, aby pobrać plik cookie skojarzony z danym `IUnknown` wskaźnikiem.|
|[CComDynamicUnkArray:: GetSize](#getsize)|Zwraca długość tablicy.|
|[CComDynamicUnkArray:: getnieznany](#getunknown)|Wywołaj tę metodę, aby uzyskać `IUnknown` wskaźnik skojarzony z danym plikiem cookie.|
|[CComDynamicUnkArray:: Remove](#remove)|Wywołaj tę metodę, aby usunąć `IUnknown` wskaźnik z tablicy.|

## <a name="remarks"></a>Uwagi

`CComDynamicUnkArray` przechowuje dynamicznie przydzieloną tablicę `IUnknown` wskaźników, każdy interfejs w punkcie połączenia. `CComDynamicUnkArray` może być używany jako parametr klasy szablonu [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) .

`CComDynamicUnkArray`Metody [BEGIN](#begin) i [End](#end) mogą służyć do zapętlenia przez wszystkie punkty połączenia (na przykład gdy zdarzenie jest wyzwalane).

Aby uzyskać szczegółowe informacje na temat automatyzacji tworzenia serwerów proxy punktu połączenia [, zobacz Dodawanie punktów połączenia do obiektu](../../atl/adding-connection-points-to-an-object.md) .

> [!NOTE]
> **Uwaga** Klasa `CComDynamicUnkArray` jest używana przez kreatora **dodawania klasy** podczas tworzenia kontrolki, która ma punkty połączenia. Jeśli chcesz ręcznie określić liczbę punktów połączenia, Zmień odwołanie z `CComDynamicUnkArray` do `CComUnkArray<` *n* `>` , gdzie *n* to liczba wymaganych punktów połączenia.

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcom. h

## <a name="ccomdynamicunkarrayadd"></a><a name="add"></a> CComDynamicUnkArray:: Add

Wywołaj tę metodę, aby dodać `IUnknown` wskaźnik do tablicy.

```
DWORD Add(IUnknown* pUnk);
```

### <a name="parameters"></a>Parametry

*Punkt*<br/>
`IUnknown`Wskaźnik, który ma zostać dodany do tablicy.

### <a name="return-value"></a>Wartość zwracana

Zwraca plik cookie skojarzony z nowo dodanym wskaźnikiem.

## <a name="ccomdynamicunkarraybegin"></a><a name="begin"></a> CComDynamicUnkArray:: BEGIN

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

## <a name="ccomdynamicunkarrayclear"></a><a name="clear"></a> CComDynamicUnkArray:: Clear

Opróżnia tablicę.

```cpp
void clear();
```

## <a name="ccomdynamicunkarrayccomdynamicunkarray"></a><a name="ccomdynamicunkarray"></a> CComDynamicUnkArray::CComDynamicUnkArray

Konstruktor.

```
CComDynamicUnkArray();
```

### <a name="remarks"></a>Uwagi

Ustawia rozmiar kolekcji na zero i inicjuje wartości NULL. Destruktor zwalnia kolekcję, w razie potrzeby.

## <a name="ccomdynamicunkarrayccomdynamicunkarray"></a><a name="dtor"></a> CComDynamicUnkArray:: ~ CComDynamicUnkArray

Destruktor.

```
~CComDynamicUnkArray();
```

### <a name="remarks"></a>Uwagi

Zwalnia zasoby przydzielone przez konstruktora klasy.

## <a name="ccomdynamicunkarrayend"></a><a name="end"></a> CComDynamicUnkArray:: end

Zwraca wskaźnik do jednego z nich poza ostatnim `IUnknown` wskaźnikiem w kolekcji.

```
IUnknown**
    end();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do `IUnknown` wskaźnika interfejsu.

## <a name="ccomdynamicunkarraygetat"></a><a name="getat"></a> CComDynamicUnkArray::GetAt

Pobiera element pod określonym indeksem.

```
IUnknown* GetAt(int nIndex);
```

### <a name="parameters"></a>Parametry

*nIndex*<br/>
Indeks elementu, który ma zostać pobrany.

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do interfejsu [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) .

## <a name="ccomdynamicunkarraygetcookie"></a><a name="getcookie"></a> CComDynamicUnkArray:: getcookas

Wywołaj tę metodę, aby pobrać plik cookie skojarzony z danym `IUnknown` wskaźnikiem.

```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```

### <a name="parameters"></a>Parametry

*ppFind*<br/>
`IUnknown`Wskaźnik, dla którego wymagany jest skojarzony plik cookie.

### <a name="return-value"></a>Wartość zwracana

Zwraca plik cookie skojarzony ze `IUnknown` wskaźnikiem lub zero, jeśli nie znaleziono pasującego `IUnknown` wskaźnika.

### <a name="remarks"></a>Uwagi

Jeśli istnieje więcej niż jedno wystąpienie tego samego `IUnknown` wskaźnika, funkcja ta zwraca plik cookie dla pierwszej z nich.

## <a name="ccomdynamicunkarraygetsize"></a><a name="getsize"></a> CComDynamicUnkArray:: GetSize

Zwraca długość tablicy.

```
int GetSize() const;
```

### <a name="return-value"></a>Wartość zwracana

Długość tablicy.

## <a name="ccomdynamicunkarraygetunknown"></a><a name="getunknown"></a> CComDynamicUnkArray:: getnieznany

Wywołaj tę metodę, aby uzyskać `IUnknown` wskaźnik skojarzony z danym plikiem cookie.

```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```

### <a name="parameters"></a>Parametry

*dwCookie*<br/>
Plik cookie, dla którego `IUnknown` wymagany jest skojarzony wskaźnik.

### <a name="return-value"></a>Wartość zwracana

Zwraca `IUnknown` wskaźnik lub wartość null, jeśli nie zostanie znaleziony pasujący plik cookie.

## <a name="ccomdynamicunkarrayremove"></a><a name="remove"></a> CComDynamicUnkArray:: Remove

Wywołaj tę metodę, aby usunąć `IUnknown` wskaźnik z tablicy.

```
BOOL Remove(DWORD dwCookie);
```

### <a name="parameters"></a>Parametry

*dwCookie*<br/>
Plik cookie odwołujący się `IUnknown` do wskaźnika, który ma zostać usunięty z tablicy.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE, jeśli wskaźnik został usunięty; w przeciwnym razie FALSE.

## <a name="see-also"></a>Zobacz też

[Klasa CComUnkArray](../../atl/reference/ccomunkarray-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)

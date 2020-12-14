---
description: 'Dowiedz się więcej na temat: Klasa CTypedPtrMap'
title: Klasa CTypedPtrMap
ms.date: 11/04/2016
f1_keywords:
- CTypedPtrMap
- AFXTEMPL/CTypedPtrMap
- AFXTEMPL/CTypedPtrMap::GetNextAssoc
- AFXTEMPL/CTypedPtrMap::Lookup
- AFXTEMPL/CTypedPtrMap::RemoveKey
- AFXTEMPL/CTypedPtrMap::SetAt
helpviewer_keywords:
- CTypedPtrMap [MFC], GetNextAssoc
- CTypedPtrMap [MFC], Lookup
- CTypedPtrMap [MFC], RemoveKey
- CTypedPtrMap [MFC], SetAt
ms.assetid: 9f377385-c6e9-4471-8b40-8fe220c50164
ms.openlocfilehash: 25476a9195fe4a522ed31937dc1e2c5156ef6792
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344994"
---
# <a name="ctypedptrmap-class"></a>Klasa CTypedPtrMap

Zapewnia bezpieczną "otokę" dla obiektów klasy wskaźników `CMapPtrToPtr` , `CMapPtrToWord` ,, `CMapWordToPtr` i `CMapStringToPtr` .

## <a name="syntax"></a>Składnia

```
template<class BASE_CLASS, class KEY, class VALUE>
class CTypedPtrMap : public BASE_CLASS
```

#### <a name="parameters"></a>Parametry

*BASE_CLASS*<br/>
Klasa bazowa klasy mapy wskaźnika o określonym typie; musi być klasą mapy wskaźnika ( `CMapPtrToPtr` , `CMapPtrToWord` , `CMapWordToPtr` lub `CMapStringToPtr` ).

*GŁÓWNYCH*<br/>
Klasa obiektu użyta jako klucz do mapy.

*VALUE*<br/>
Klasa obiektu przechowywanego na mapie.

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CTypedPtrMap::GetNextAssoc](#getnextassoc)|Pobiera następny element do iteracji.|
|[CTypedPtrMap:: Lookup](#lookup)|Zwraca wartość na `KEY` podstawie `VALUE` .|
|[CTypedPtrMap::RemoveKey](#removekey)|Usuwa element określony przez klucz.|
|[CTypedPtrMap::SetAt](#setat)|Wstawia element do mapy; Zastępuje istniejący element, jeśli zostanie znaleziony pasujący klucz.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CTypedPtrMap:: operator \[\]](#operator_at)|Wstawia element do mapy.|

## <a name="remarks"></a>Uwagi

W przypadku korzystania `CTypedPtrMap` z funkcji sprawdzania typu C++ pomaga wyeliminować błędy spowodowane niezgodnymi typami wskaźnika.

Ponieważ wszystkie `CTypedPtrMap` funkcje są wbudowane, użycie tego szablonu nie ma znacząco wpływu na rozmiar lub szybkość kodu.

Aby uzyskać więcej informacji na temat korzystania z programu `CTypedPtrMap` , zobacz [kolekcje](../../mfc/collections.md) artykułów i [klasy oparte na szablonach](../../mfc/template-based-classes.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`BASE_CLASS`

`CTypedPtrMap`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxtempl. h

## <a name="ctypedptrmapgetnextassoc"></a><a name="getnextassoc"></a> CTypedPtrMap::GetNextAssoc

Pobiera element mapy w `rNextPosition` , a następnie aktualizuje, `rNextPosition` Aby odwołać się do następnego elementu na mapie.

```cpp
void GetNextAssoc(
    POSITION& rPosition,
    KEY& rKey,
    VALUE& rValue) const;
```

### <a name="parameters"></a>Parametry

*Elemencie rPosition*<br/>
Określa odwołanie do wartości pozycji zwróconej przez poprzednie `GetNextAssoc` wywołanie lub `BASE_CLASS` **:: GetStartPosition** .

*GŁÓWNYCH*<br/>
Parametr szablonu określający typ kluczy mapy.

*rKey*<br/>
Określa zwracany klucz pobranego elementu.

*VALUE*<br/>
Parametr szablonu określający typ wartości mapy.

*rValue*<br/>
Określa zwróconą wartość pobranego elementu.

### <a name="remarks"></a>Uwagi

Ta funkcja jest najbardziej przydatna do iterowania przez wszystkie elementy na mapie. Należy zauważyć, że sekwencja położenia nie musi być taka sama jak sekwencja wartości klucza.

Jeśli pobrany element jest ostatnim na mapie, Nowa wartość jest równa `rNextPosition` null.

Ta wbudowana funkcja wywołuje `BASE_CLASS` **:: GetNextAssoc**.

## <a name="ctypedptrmaplookup"></a><a name="lookup"></a> CTypedPtrMap:: Lookup

`Lookup` używa algorytmu wyznaczania wartości skrótu, aby szybko znaleźć element mapy z kluczem, który dokładnie pasuje.

```
BOOL Lookup(BASE_CLASS ::BASE_ARG_KEY key, VALUE& rValue) const;
```

### <a name="parameters"></a>Parametry

*BASE_CLASS*<br/>
Parametr szablonu określający klasę bazową klasy tej mapy.

*głównych*<br/>
Klucz elementu, który ma zostać wyszukany.

*VALUE*<br/>
Parametr szablonu określający typ wartości przechowywanych w tej mapie.

*rValue*<br/>
Określa zwróconą wartość pobranego elementu.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli element został znaleziony; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Ta wbudowana funkcja wywołuje `BASE_CLASS` **:: Lookup**.

## <a name="ctypedptrmapoperator--"></a><a name="operator_at"></a> CTypedPtrMap:: operator []

Tego operatora można używać tylko po lewej stronie instrukcji przypisania (wartość l).

```
VALUE& operator[ ](base_class ::base_arg_key key);
```

### <a name="parameters"></a>Parametry

*VALUE*<br/>
Parametr szablonu określający typ wartości przechowywanych w tej mapie.

*BASE_CLASS*<br/>
Parametr szablonu określający klasę bazową klasy tej mapy.

*głównych*<br/>
Klucz elementu do wyszukania lub utworzenia na mapie.

### <a name="remarks"></a>Uwagi

Jeśli nie ma elementu mapy o określonym kluczu, zostanie utworzony nowy element. Nie ma "prawa strona" (r-Value) równoważnej temu operatorowi, ponieważ istnieje możliwość, że klucz może nie zostać znaleziony na mapie. Użyj `Lookup` funkcji członkowskiej do pobierania elementów.

## <a name="ctypedptrmapremovekey"></a><a name="removekey"></a> CTypedPtrMap::RemoveKey

Ta funkcja elementu członkowskiego wywołuje `BASE_CLASS` **:: RemoveKey**.

```
BOOL RemoveKey(KEY key);
```

### <a name="parameters"></a>Parametry

*GŁÓWNYCH*<br/>
Parametr szablonu określający typ kluczy mapy.

*głównych*<br/>
Klucz dla elementu, który ma zostać usunięty.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, Jeśli wpis został znaleziony i pomyślnie usunięty; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Aby uzyskać bardziej szczegółowe uwagi, zobacz [CMapStringToOb:: RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey).

## <a name="ctypedptrmapsetat"></a><a name="setat"></a> CTypedPtrMap::SetAt

Ta funkcja elementu członkowskiego wywołuje `BASE_CLASS` **:: SetAt**.

```cpp
void SetAt(KEY key, VALUE newValue);
```

### <a name="parameters"></a>Parametry

*GŁÓWNYCH*<br/>
Parametr szablonu określający typ kluczy mapy.

*głównych*<br/>
Określa wartość klucza newValue.

*newValue*<br/>
Określa wskaźnik obiektu, który jest wartością nowego elementu.

### <a name="remarks"></a>Uwagi

Aby uzyskać bardziej szczegółowe uwagi, zobacz [CMapStringToOb:: SetAt](../../mfc/reference/cmapstringtoob-class.md#setat).

## <a name="see-also"></a>Zobacz też

[ZBIERANIE próbek MFC](../../overview/visual-cpp-samples.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)<br/>
[Klasa CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)<br/>
[Klasa CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)<br/>
[Klasa CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)

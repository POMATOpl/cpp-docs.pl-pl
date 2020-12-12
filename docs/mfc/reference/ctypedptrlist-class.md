---
description: 'Dowiedz się więcej na temat: Klasa CTypedPtrList'
title: Klasa CTypedPtrList
ms.date: 11/04/2016
f1_keywords:
- CTypedPtrList
- AFXTEMPL/CTypedPtrList
- AFXTEMPL/CTypedPtrList::AddHead
- AFXTEMPL/CTypedPtrList::AddTail
- AFXTEMPL/CTypedPtrList::GetAt
- AFXTEMPL/CTypedPtrList::GetHead
- AFXTEMPL/CTypedPtrList::GetNext
- AFXTEMPL/CTypedPtrList::GetPrev
- AFXTEMPL/CTypedPtrList::GetTail
- AFXTEMPL/CTypedPtrList::RemoveHead
- AFXTEMPL/CTypedPtrList::RemoveTail
- AFXTEMPL/CTypedPtrList::SetAt
helpviewer_keywords:
- CTypedPtrList [MFC], AddHead
- CTypedPtrList [MFC], AddTail
- CTypedPtrList [MFC], GetAt
- CTypedPtrList [MFC], GetHead
- CTypedPtrList [MFC], GetNext
- CTypedPtrList [MFC], GetPrev
- CTypedPtrList [MFC], GetTail
- CTypedPtrList [MFC], RemoveHead
- CTypedPtrList [MFC], RemoveTail
- CTypedPtrList [MFC], SetAt
ms.assetid: c273096e-1756-4340-864b-4a08b674a65e
ms.openlocfilehash: 353e9af00b1366b260ce3cb3689018a8e4e370c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318536"
---
# <a name="ctypedptrlist-class"></a>Klasa CTypedPtrList

Zapewnia bezpieczną "otokę" dla obiektów klasy `CPtrList` .

## <a name="syntax"></a>Składnia

```
template<class BASE_CLASS, class TYPE>
class CTypedPtrList : public BASE_CLASS
```

#### <a name="parameters"></a>Parametry

*BASE_CLASS*<br/>
Klasa bazowa klasy listy wskaźników o określonym typie; musi być klasą listy wskaźników ( `CObList` lub `CPtrList` ).

*TYP*<br/>
Typ elementów przechowywanych na liście klas podstawowych.

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CTypedPtrList:: addszef](#addhead)|Dodaje element (lub wszystkie elementy z innej listy) do nagłówka listy (tworzy nowy nagłówek).|
|[CTypedPtrList:: AddTail](#addtail)|Dodaje element (lub wszystkie elementy z innej listy) do ogona listy (tworzy nowy ogon).|
|[CTypedPtrList::GetAt](#getat)|Pobiera element w danym położeniu.|
|[CTypedPtrList:: getszef](#gethead)|Zwraca element główny listy (nie może być pusty).|
|[CTypedPtrList:: GetNext](#getnext)|Pobiera następny element do iteracji.|
|[CTypedPtrList:: getpoprz](#getprev)|Pobiera poprzedni element do iteracji.|
|[CTypedPtrList:: GetTail](#gettail)|Zwraca element końcowy listy (nie może być pusty).|
|[CTypedPtrList::RemoveHead](#removehead)|Usuwa element z nagłówka listy.|
|[CTypedPtrList::RemoveTail](#removetail)|Usuwa element z ogona listy.|
|[CTypedPtrList::SetAt](#setat)|Ustawia element w danym położeniu.|

## <a name="remarks"></a>Uwagi

Gdy używasz `CTypedPtrList` , a nie `CObList` lub `CPtrList` , funkcja sprawdzania typu C++ pomaga wyeliminować błędy spowodowane niezgodnymi typami wskaźnika.

Ponadto `CTypedPtrList` otoka wykonuje większość rzutowania, które byłyby wymagane, jeśli użyto `CObList` lub `CPtrList` .

Ponieważ wszystkie `CTypedPtrList` funkcje są wbudowane, użycie tego szablonu nie ma znacząco wpływu na rozmiar lub szybkość kodu.

Listy pochodne `CObList` można serializować, ale te pochodne od `CPtrList` nie mogą.

Po `CTypedPtrList` usunięciu obiektu lub po usunięciu jego elementów zostaną usunięte tylko te wskaźniki, a nie jednostki, do których się odwołują.

Aby uzyskać więcej informacji na temat korzystania z programu `CTypedPtrList` , zobacz [kolekcje](../../mfc/collections.md) artykułów i [klasy oparte na szablonach](../../mfc/template-based-classes.md).

## <a name="example"></a>Przykład

Ten przykład tworzy wystąpienie `CTypedPtrList` , dodaje jeden obiekt, serializować listę do dysku, a następnie usuwa obiekt:

[!code-cpp[NVC_MFCCollections#110](../../mfc/codesnippet/cpp/ctypedptrlist-class_1.cpp)]

[!code-cpp[NVC_MFCCollections#111](../../mfc/codesnippet/cpp/ctypedptrlist-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`BASE_CLASS`

`_CTypedPtrList`

`CTypedPtrList`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxtempl. h

## <a name="ctypedptrlistaddhead"></a><a name="addhead"></a> CTypedPtrList:: addszef

Ta funkcja elementu członkowskiego wywołuje `BASE_CLASS` **:: addszef**.

```
POSITION AddHead(TYPE newElement);
void AddHead(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```

### <a name="parameters"></a>Parametry

*TYP*<br/>
Typ elementów przechowywanych na liście klas podstawowych.

*newElement*<br/>
Wskaźnik obiektu, który ma zostać dodany do tej listy. Dozwolona jest wartość NULL.

*BASE_CLASS*<br/>
Klasa bazowa klasy listy wskaźników o określonym typie; musi być klasą listy wskaźników ( [CObList](../../mfc/reference/coblist-class.md) lub [CPtrList](../../mfc/reference/cptrlist-class.md)).

*pNewList*<br/>
Wskaźnik do innego obiektu [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md) . Elementy w *pNewList* zostaną dodane do tej listy.

### <a name="return-value"></a>Wartość zwracana

Pierwsza wersja zwraca wartość pozycji nowo wstawionego elementu.

### <a name="remarks"></a>Uwagi

Pierwsza wersja dodaje nowy element przed nagłówkiem listy. Druga wersja dodaje kolejną listę elementów przed nagłówkiem.

## <a name="ctypedptrlistaddtail"></a><a name="addtail"></a> CTypedPtrList:: AddTail

Ta funkcja elementu członkowskiego wywołuje `BASE_CLASS` **:: AddTail**.

```
POSITION AddTail(TYPE newElement);
void AddTail(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```

### <a name="parameters"></a>Parametry

*TYP*<br/>
Typ elementów przechowywanych na liście klas podstawowych.

*newElement*<br/>
Wskaźnik obiektu, który ma zostać dodany do tej listy. Dozwolona jest wartość NULL.

*BASE_CLASS*<br/>
Klasa bazowa klasy listy wskaźników o określonym typie; musi być klasą listy wskaźników ( [CObList](../../mfc/reference/coblist-class.md) lub [CPtrList](../../mfc/reference/cptrlist-class.md)).

*pNewList*<br/>
Wskaźnik do innego obiektu [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md) . Elementy w *pNewList* zostaną dodane do tej listy.

### <a name="return-value"></a>Wartość zwracana

Pierwsza wersja zwraca wartość pozycji nowo wstawionego elementu.

### <a name="remarks"></a>Uwagi

Pierwsza wersja dodaje nowy element po końcu listy. Druga wersja dodaje kolejną listę elementów po końcu listy.

## <a name="ctypedptrlistgetat"></a><a name="getat"></a> CTypedPtrList::GetAt

Zmienna typu pozycja jest kluczem dla listy.

```
TYPE& GetAt(POSITION position);
TYPE GetAt(POSITION position) const;
```

### <a name="parameters"></a>Parametry

*TYP*<br/>
Parametr szablonu określający typ elementów przechowywanych na liście.

*umieścić*<br/>
Wartość pozycji zwrócona przez poprzednie `GetHeadPosition` lub `Find` wywołanie funkcji składowej.

### <a name="return-value"></a>Wartość zwracana

Jeśli dostęp do listy jest uzyskiwany za pomocą wskaźnika do `const CTypedPtrList` , a następnie `GetAt` zwraca wskaźnik typu określonego przez *Typ* parametru szablonu. Dzięki temu funkcja może być używana tylko po prawej stronie instrukcji przypisania i w ten sposób chroni listę przed modyfikacją.

Jeśli lista jest dostępna bezpośrednio lub za pomocą wskaźnika do `CTypedPtrList` , a następnie `GetAt` zwraca odwołanie do wskaźnika typu określonego przez *Typ* parametru szablonu. Dzięki temu funkcja może być używana po obu stronach instrukcji przypisania i w ten sposób zezwala na modyfikowanie wpisów listy.

### <a name="remarks"></a>Uwagi

Nie jest taki sam jak indeks i nie można wykonać operacji na wartości pozycji samodzielnie. `GetAt` Pobiera `CObject` wskaźnik skojarzony z daną pozycją.

Musisz się upewnić, że wartość pozycji reprezentuje prawidłową pozycję na liście. Jeśli jest nieprawidłowa, wersja debugowana biblioteka MFC potwierdzenia.

Ta wbudowana funkcja wywołuje `BASE_CLASS` **:: GetAt**.

## <a name="ctypedptrlistgethead"></a><a name="gethead"></a> CTypedPtrList:: getszef

Pobiera wskaźnik reprezentujący element nagłówka tej listy.

```
TYPE& GetHead();
TYPE GetHead() const;
```

### <a name="parameters"></a>Parametry

*TYP*<br/>
Parametr szablonu określający typ elementów przechowywanych na liście.

### <a name="return-value"></a>Wartość zwracana

Jeśli dostęp do listy jest uzyskiwany za pomocą wskaźnika do `const CTypedPtrList` , a następnie `GetHead` zwraca wskaźnik typu określonego przez *Typ* parametru szablonu. Dzięki temu funkcja może być używana tylko po prawej stronie instrukcji przypisania i w ten sposób chroni listę przed modyfikacją.

Jeśli lista jest dostępna bezpośrednio lub za pomocą wskaźnika do `CTypedPtrList` , a następnie `GetHead` zwraca odwołanie do wskaźnika typu określonego przez *Typ* parametru szablonu. Dzięki temu funkcja może być używana po obu stronach instrukcji przypisania i w ten sposób zezwala na modyfikowanie wpisów listy.

### <a name="remarks"></a>Uwagi

Przed wywołaniem należy upewnić się, że lista nie jest pusta `GetHead` . Jeśli lista jest pusta, wówczas wersja do debugowania biblioteka MFC potwierdzenia. Użyj [IsEmpty](../../mfc/reference/coblist-class.md#isempty) , aby sprawdzić, czy lista zawiera elementy.

## <a name="ctypedptrlistgetnext"></a><a name="getnext"></a> CTypedPtrList:: GetNext

Pobiera element list identyfikowany przez *elemencie rPosition*, a następnie ustawia *elemencie RPOSITION* na wartość pozycji następnego wpisu na liście.

```
TYPE& GetNext(POSITION& rPosition);
TYPE GetNext(POSITION& rPosition) const;
```

### <a name="parameters"></a>Parametry

*TYP*<br/>
Parametr szablonu określający typ elementów zawartych na tej liście.

*Elemencie rPosition*<br/>
Odwołanie do wartości pozycji zwróconej przez poprzednie `GetNext` , `GetHeadPosition` lub inne wywołanie funkcji składowej.

### <a name="return-value"></a>Wartość zwracana

Jeśli dostęp do listy jest uzyskiwany za pomocą wskaźnika do `const CTypedPtrList` , a następnie `GetNext` zwraca wskaźnik typu określonego przez *Typ* parametru szablonu. Dzięki temu funkcja może być używana tylko po prawej stronie instrukcji przypisania i w ten sposób chroni listę przed modyfikacją.

Jeśli lista jest dostępna bezpośrednio lub za pomocą wskaźnika do `CTypedPtrList` , a następnie `GetNext` zwraca odwołanie do wskaźnika typu określonego przez *Typ* parametru szablonu. Dzięki temu funkcja może być używana po obu stronach instrukcji przypisania i w ten sposób zezwala na modyfikowanie wpisów listy.

### <a name="remarks"></a>Uwagi

Można użyć `GetNext` w pętli iteracji do przodu w przypadku ustanowienia początkowej pozycji z wywołaniem `GetHeadPosition` lub [CPtrList:: find](../../mfc/reference/coblist-class.md#find).

Musisz się upewnić, że wartość pozycji reprezentuje prawidłową pozycję na liście. Jeśli jest nieprawidłowa, wersja debugowana biblioteka MFC potwierdzenia.

Jeśli pobrany element jest ostatni na liście, Nowa wartość *elemencie rPosition* jest ustawiona na wartość null.

Istnieje możliwość usunięcia elementu podczas iteracji. Zobacz przykład dla [CObList:: RemoveAt](../../mfc/reference/coblist-class.md#removeat).

## <a name="ctypedptrlistgetprev"></a><a name="getprev"></a> CTypedPtrList:: getpoprz

Pobiera element list identyfikowany przez *elemencie rPosition*, a następnie ustawia *elemencie RPOSITION* na wartość pozycji poprzedniej pozycji na liście.

```
TYPE& GetPrev(POSITION& rPosition);
TYPE GetPrev(POSITION& rPosition) const;
```

### <a name="parameters"></a>Parametry

*TYP*<br/>
Parametr szablonu określający typ elementów zawartych na tej liście.

*Elemencie rPosition*<br/>
Odwołanie do wartości pozycji zwróconej przez poprzednie `GetPrev` lub inne wywołanie funkcji składowej.

### <a name="return-value"></a>Wartość zwracana

Jeśli dostęp do listy jest uzyskiwany za pomocą wskaźnika do `const CTypedPtrList` , a następnie `GetPrev` zwraca wskaźnik typu określonego przez *Typ* parametru szablonu. Dzięki temu funkcja może być używana tylko po prawej stronie instrukcji przypisania i w ten sposób chroni listę przed modyfikacją.

Jeśli lista jest dostępna bezpośrednio lub za pomocą wskaźnika do `CTypedPtrList` , a następnie `GetPrev` zwraca odwołanie do wskaźnika typu określonego przez *Typ* parametru szablonu. Dzięki temu funkcja może być używana po obu stronach instrukcji przypisania i w ten sposób zezwala na modyfikowanie wpisów listy.

### <a name="remarks"></a>Uwagi

Można użyć `GetPrev` w pętli wstecznej iteracji, jeśli zostanie nadana początkowa pozycja z wywołaniem `GetTailPosition` lub `Find` .

Musisz się upewnić, że wartość pozycji reprezentuje prawidłową pozycję na liście. Jeśli jest nieprawidłowa, wersja debugowana biblioteka MFC potwierdzenia.

Jeśli pobrany element jest pierwszy na liście, Nowa wartość *elemencie rPosition* jest ustawiona na wartość null.

## <a name="ctypedptrlistgettail"></a><a name="gettail"></a> CTypedPtrList:: GetTail

Pobiera wskaźnik reprezentujący element nagłówka tej listy.

```
TYPE& GetTail();
TYPE GetTail() const;
```

### <a name="parameters"></a>Parametry

*TYP*<br/>
Parametr szablonu określający typ elementów przechowywanych na liście.

### <a name="return-value"></a>Wartość zwracana

Jeśli dostęp do listy jest uzyskiwany za pomocą wskaźnika do `const CTypedPtrList` , a następnie `GetTail` zwraca wskaźnik typu określonego przez *Typ* parametru szablonu. Dzięki temu funkcja może być używana tylko po prawej stronie instrukcji przypisania i w ten sposób chroni listę przed modyfikacją.

Jeśli lista jest dostępna bezpośrednio lub za pomocą wskaźnika do `CTypedPtrList` , a następnie `GetTail` zwraca odwołanie do wskaźnika typu określonego przez *Typ* parametru szablonu. Dzięki temu funkcja może być używana po obu stronach instrukcji przypisania i w ten sposób zezwala na modyfikowanie wpisów listy.

### <a name="remarks"></a>Uwagi

Przed wywołaniem należy upewnić się, że lista nie jest pusta `GetTail` . Jeśli lista jest pusta, wówczas wersja do debugowania biblioteka MFC potwierdzenia. Użyj [IsEmpty](../../mfc/reference/coblist-class.md#isempty) , aby sprawdzić, czy lista zawiera elementy.

## <a name="ctypedptrlistremovehead"></a><a name="removehead"></a> CTypedPtrList::RemoveHead

Usuwa element z nagłówka listy i zwraca go.

```
TYPE RemoveHead();
```

### <a name="parameters"></a>Parametry

*TYP*<br/>
Parametr szablonu określający typ elementów przechowywanych na liście.

### <a name="return-value"></a>Wartość zwracana

Wskaźnik wcześniej umieszczony na początku listy. Ten wskaźnik jest typu określonego przez *Typ* parametru szablonu.

### <a name="remarks"></a>Uwagi

Przed wywołaniem należy upewnić się, że lista nie jest pusta `RemoveHead` . Jeśli lista jest pusta, wówczas wersja do debugowania biblioteka MFC potwierdzenia. Użyj [IsEmpty](../../mfc/reference/coblist-class.md#isempty) , aby sprawdzić, czy lista zawiera elementy.

## <a name="ctypedptrlistremovetail"></a><a name="removetail"></a> CTypedPtrList::RemoveTail

Usuwa element z ogona listy i zwraca go.

```
TYPE RemoveTail();
```

### <a name="parameters"></a>Parametry

*TYP*<br/>
Parametr szablonu określający typ elementów przechowywanych na liście.

### <a name="return-value"></a>Wartość zwracana

Wskaźnik wcześniej na końcu listy. Ten wskaźnik jest typu określonego przez *Typ* parametru szablonu.

### <a name="remarks"></a>Uwagi

Przed wywołaniem należy upewnić się, że lista nie jest pusta `RemoveTail` . Jeśli lista jest pusta, wówczas wersja do debugowania biblioteka MFC potwierdzenia. Użyj [IsEmpty](../../mfc/reference/coblist-class.md#isempty) , aby sprawdzić, czy lista zawiera elementy.

## <a name="ctypedptrlistsetat"></a><a name="setat"></a> CTypedPtrList::SetAt

Ta funkcja elementu członkowskiego wywołuje `BASE_CLASS` **:: SetAt**.

```cpp
void SetAt(POSITION pos, TYPE newElement);
```

### <a name="parameters"></a>Parametry

*Terminal*<br/>
Pozycja elementu, który ma zostać ustawiony.

*TYP*<br/>
Typ elementów przechowywanych na liście klas podstawowych.

*newElement*<br/>
Wskaźnik obiektu, który ma zostać zapisany na liście.

### <a name="remarks"></a>Uwagi

Zmienna typu pozycja jest kluczem dla listy. Nie jest taki sam jak indeks i nie można wykonać operacji na wartości pozycji samodzielnie. `SetAt` zapisuje wskaźnik obiektu do określonej pozycji na liście.

Musisz się upewnić, że wartość pozycji reprezentuje prawidłową pozycję na liście. Jeśli jest nieprawidłowa, wersja debugowana biblioteka MFC potwierdzenia.

Aby uzyskać bardziej szczegółowe uwagi, zobacz [CObList:: SetAt](../../mfc/reference/coblist-class.md#setat).

## <a name="see-also"></a>Zobacz też

[ZBIERANIE próbek MFC](../../overview/visual-cpp-samples.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa CPtrList](../../mfc/reference/cptrlist-class.md)<br/>
[Klasa CObList](../../mfc/reference/coblist-class.md)

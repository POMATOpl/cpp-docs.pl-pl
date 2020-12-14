---
description: 'Dowiedz się więcej na temat: Klasa CStringList'
title: Klasa CStringList
ms.date: 11/04/2016
f1_keywords:
- CStringList
- AFXCOLL/CStringList
- AFXCOLL/CStringList::CStringList
- AFXCOLL/CStringList::AddHead
- AFXCOLL/CStringList::AddTail
- AFXCOLL/CStringList::Find
- AFXCOLL/CStringList::FindIndex
- AFXCOLL/CStringList::GetAt
- AFXCOLL/CStringList::GetCount
- AFXCOLL/CStringList::GetHead
- AFXCOLL/CStringList::GetHeadPosition
- AFXCOLL/CStringList::GetNext
- AFXCOLL/CStringList::GetPrev
- AFXCOLL/CStringList::GetSize
- AFXCOLL/CStringList::GetTail
- AFXCOLL/CStringList::GetTailPosition
- AFXCOLL/CStringList::InsertAfter
- AFXCOLL/CStringList::InsertBefore
- AFXCOLL/CStringList::IsEmpty
- AFXCOLL/CStringList::RemoveAll
- AFXCOLL/CStringList::RemoveAt
- AFXCOLL/CStringList::RemoveHead
- AFXCOLL/CStringList::RemoveTail
- AFXCOLL/CStringList::SetAt
helpviewer_keywords:
- CStringList [MFC], CStringList
- CStringList [MFC], AddHead
- CStringList [MFC], AddTail
- CStringList [MFC], Find
- CStringList [MFC], FindIndex
- CStringList [MFC], GetAt
- CStringList [MFC], GetCount
- CStringList [MFC], GetHead
- CStringList [MFC], GetHeadPosition
- CStringList [MFC], GetNext
- CStringList [MFC], GetPrev
- CStringList [MFC], GetSize
- CStringList [MFC], GetTail
- CStringList [MFC], GetTailPosition
- CStringList [MFC], InsertAfter
- CStringList [MFC], InsertBefore
- CStringList [MFC], IsEmpty
- CStringList [MFC], RemoveAll
- CStringList [MFC], RemoveAt
- CStringList [MFC], RemoveHead
- CStringList [MFC], RemoveTail
- CStringList [MFC], SetAt
ms.assetid: 310a7edb-263c-4bd2-ac43-0bfbfddc5a33
ms.openlocfilehash: c9043ef648f50e880f3b5946c1912deca3de6714
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345072"
---
# <a name="cstringlist-class"></a>Klasa CStringList

Obsługuje listy `CString` obiektów.

## <a name="syntax"></a>Składnia

```
class CStringList : public CObject
```

## <a name="members"></a>Elementy członkowskie

Funkcje składowe `CStringList` są podobne do funkcji składowych klasy [CObList](../../mfc/reference/coblist-class.md). W związku z tym podobieństwem można użyć `CObList` dokumentacji referencyjnej dla specyficznych dla funkcji składowych. Wszędzie tam, gdzie widzisz `CObject` wskaźnik jako wartość zwrotną, podstaw `CString` (nie `CString` wskaźnik). Wszędzie tam, gdzie widzisz `CObject` wskaźnik jako parametr funkcji, podstaw `LPCTSTR` .

`CObject*& CObList::GetHead() const;`

na przykład tłumaczy na

`CString& CStringList::GetHead() const;`

oraz

`POSITION AddHead( CObject* <newElement> );`

tłumaczy na

`POSITION AddHead( LPCTSTR <newElement> );`

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CStringList::CStringList](../../mfc/reference/coblist-class.md#coblist)|Tworzy pustą listę.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CStringList:: addszef](../../mfc/reference/coblist-class.md#addhead)|Dodaje element (lub wszystkie elementy z innej listy) do nagłówka listy (tworzy nowy nagłówek).|
|[CStringList:: AddTail](../../mfc/reference/coblist-class.md#addtail)|Dodaje element (lub wszystkie elementy z innej listy) do ogona listy (tworzy nowy ogon).|
|[CStringList:: find](../../mfc/reference/coblist-class.md#find)|Pobiera pozycję elementu określonego przez wartość wskaźnika.|
|[CStringList:: FindIndex —](../../mfc/reference/coblist-class.md#findindex)|Pobiera pozycję elementu określonego przez indeks (liczony od zera).|
|[CStringList::GetAt](../../mfc/reference/coblist-class.md#getat)|Pobiera element w danym położeniu.|
|[CStringList:: GetCount](../../mfc/reference/coblist-class.md#getcount)|Zwraca liczbę elementów na liście.|
|[CStringList:: getszef](../../mfc/reference/coblist-class.md#gethead)|Zwraca element główny listy (nie może być pusty).|
|[CStringList::GetHeadPosition](../../mfc/reference/coblist-class.md#getheadposition)|Zwraca pozycję elementu nagłówkowego listy.|
|[CStringList:: GetNext](../../mfc/reference/coblist-class.md#getnext)|Pobiera następny element do iteracji.|
|[CStringList:: getpoprz](../../mfc/reference/coblist-class.md#getprev)|Pobiera poprzedni element do iteracji.|
|[CStringList:: GetSize](../../mfc/reference/coblist-class.md#getsize)|Zwraca liczbę elementów na liście.|
|[CStringList:: GetTail](../../mfc/reference/coblist-class.md#gettail)|Zwraca element końcowy listy (nie może być pusty).|
|[CStringList::GetTailPosition](../../mfc/reference/coblist-class.md#gettailposition)|Zwraca pozycję elementu ogona listy.|
|[CStringList::InsertAfter](../../mfc/reference/coblist-class.md#insertafter)|Wstawia nowy element po danej pozycji.|
|[CStringList::InsertBefore](../../mfc/reference/coblist-class.md#insertbefore)|Wstawia nowy element przed daną pozycją.|
|[CStringList:: IsEmpty](../../mfc/reference/coblist-class.md#isempty)|Testy dla warunku pustej listy (brak elementów).|
|[CStringList::](../../mfc/reference/coblist-class.md#removeall)|Usuwa wszystkie elementy z tej listy.|
|[CStringList::RemoveAt](../../mfc/reference/coblist-class.md#removeat)|Usuwa element z tej listy, określony według pozycji.|
|[CStringList::RemoveHead](../../mfc/reference/coblist-class.md#removehead)|Usuwa element z nagłówka listy.|
|[CStringList::RemoveTail](../../mfc/reference/coblist-class.md#removetail)|Usuwa element z ogona listy.|
|[CStringList::SetAt](../../mfc/reference/coblist-class.md#setat)|Ustawia element w danym położeniu.|

## <a name="remarks"></a>Uwagi

Wszystkie porównania są wykonywane przez wartość, co oznacza, że znaki w ciągu są porównywane zamiast adresów ciągów.

`CStringList` obejmuje IMPLEMENT_SERIAL makro do obsługi serializacji i dumpingu jego elementów. Jeśli lista `CString` obiektów jest przechowywana w archiwum, z przeładowanym operatorem wstawiania lub `Serialize` funkcją składową, każdy `CString` element jest serializowany z kolei.

Jeśli potrzebujesz zrzutu poszczególnych `CString` elementów, musisz ustawić głębokość kontekstu zrzutu na 1 lub większą.

Aby uzyskać więcej informacji na temat korzystania z programu `CStringList` , zobacz [kolekcje](../../mfc/collections.md)artykułów.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

`CStringList`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxcoll. h

## <a name="see-also"></a>Zobacz też

[ZBIERANIE próbek MFC](../../overview/visual-cpp-samples.md)<br/>
[Klasa CObject](../../mfc/reference/cobject-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)

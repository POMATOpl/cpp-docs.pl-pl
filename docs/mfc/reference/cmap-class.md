---
description: 'Dowiedz się więcej na temat: Klasa CMap'
title: Klasa CMap
ms.date: 11/04/2016
f1_keywords:
- CMap
- AFXTEMPL/CMap
- AFXTEMPL/CMap::CPair
- AFXTEMPL/CMap::CMap
- AFXTEMPL/CMap::GetCount
- AFXTEMPL/CMap::GetHashTableSize
- AFXTEMPL/CMap::GetNextAssoc
- AFXTEMPL/CMap::GetSize
- AFXTEMPL/CMap::GetStartPosition
- AFXTEMPL/CMap::InitHashTable
- AFXTEMPL/CMap::IsEmpty
- AFXTEMPL/CMap::Lookup
- AFXTEMPL/CMap::PGetFirstAssoc
- AFXTEMPL/CMap::PGetNextAssoc
- AFXTEMPL/CMap::PLookup
- AFXTEMPL/CMap::RemoveAll
- AFXTEMPL/CMap::RemoveKey
- AFXTEMPL/CMap::SetAt
helpviewer_keywords:
- CMap [MFC], CPair
- CMap [MFC], CMap
- CMap [MFC], GetCount
- CMap [MFC], GetHashTableSize
- CMap [MFC], GetNextAssoc
- CMap [MFC], GetSize
- CMap [MFC], GetStartPosition
- CMap [MFC], InitHashTable
- CMap [MFC], IsEmpty
- CMap [MFC], Lookup
- CMap [MFC], PGetFirstAssoc
- CMap [MFC], PGetNextAssoc
- CMap [MFC], PLookup
- CMap [MFC], RemoveAll
- CMap [MFC], RemoveKey
- CMap [MFC], SetAt
ms.assetid: 640a45ab-0993-4def-97ec-42cc78eb10b9
ms.openlocfilehash: ff88d205608cc87f06d28e6d2d4b647c35909efa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207907"
---
# <a name="cmap-class"></a>Klasa CMap

Klasa kolekcji słownika, która mapuje unikatowe klucze na wartości.

## <a name="syntax"></a>Składnia

```
template<class KEY, class ARG_KEY, class VALUE, class ARG_VALUE>class CMap : public CObject
```

#### <a name="parameters"></a>Parametry

*GŁÓWNYCH*<br/>
Klasa obiektu użyta jako klucz do mapy.

*ARG_KEY*<br/>
Typ danych używany dla argumentów *klucza* ; zwykle odwołanie do *klucza*.

*VALUE*<br/>
Klasa obiektu przechowywanego na mapie.

*ARG_VALUE*<br/>
Typ danych używany dla argumentów *wartości* ; zwykle odwołanie do *wartości*.

## <a name="members"></a>Elementy członkowskie

### <a name="public-structures"></a>Struktury publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMap::CPair](#cpair)|Zagnieżdżona struktura zawierająca wartość klucza i wartość skojarzonego obiektu.|

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMap::CMap](#cmap)|Tworzy kolekcję, która mapuje klucze na wartości.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMap:: GetCount](#getcount)|Zwraca liczbę elementów w tej mapie.|
|[CMap::GetHashTableSize](#gethashtablesize)|Zwraca liczbę elementów w tabeli skrótów.|
|[CMap::GetNextAssoc](#getnextassoc)|Pobiera następny element do iteracji.|
|[CMap:: GetSize](#getsize)|Zwraca liczbę elementów w tej mapie.|
|[CMap::GetStartPosition](#getstartposition)|Zwraca pozycję pierwszego elementu.|
|[CMap::InitHashTable](#inithashtable)|Inicjuje tabelę skrótów i określa jej rozmiar.|
|[CMap:: IsEmpty](#isempty)|Testuje warunek pustej mapy (nie elementy).|
|[CMap:: Lookup](#lookup)|Wyszukuje wartość zamapowane na dany klucz.|
|[CMap::P GetFirstAssoc](#pgetfirstassoc)|Zwraca wskaźnik do pierwszego elementu.|
|[CMap::P GetNextAssoc](#pgetnextassoc)|Pobiera wskaźnik do następnego elementu do iteracji.|
|[CMap: wyszukiwanie:P](#plookup)|Zwraca wskaźnik do klucza, którego wartość jest zgodna z określoną wartością.|
|[CMAP::](#removeall)|Usuwa wszystkie elementy z tej mapy.|
|[CMap::RemoveKey](#removekey)|Usuwa element określony przez klucz.|
|[CMap::SetAt](#setat)|Wstawia element do mapy; Zastępuje istniejący element, jeśli zostanie znaleziony pasujący klucz.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMap:: operator \[\]](#operator_at)|Wstawia element do mapy — podstawienia operatora dla `SetAt` .|

## <a name="remarks"></a>Uwagi

Po wstawieniu pary klucz-wartość (element) do mapy można efektywnie pobrać lub usunąć parę przy użyciu klucza, aby uzyskać do niego dostęp. Możesz również wykonać iterację wszystkich elementów na mapie.

Zmienna typu pozycja jest używana na potrzeby alternatywnego dostępu do wpisów. Możesz użyć pozycji do "zapamiętać" wpisu i iteracji przez mapę. Można sądzić, że ta Iteracja jest sekwencyjna według wartości klucza; nie jest. Sekwencja pobranych elementów jest nieokreślona.

Niektóre funkcje członkowskie tej klasy wywołują globalne funkcje pomocnika, które muszą być dostosowane do większości zastosowania `CMap` klasy. Zobacz [pomocników klasy kolekcji](../../mfc/reference/collection-class-helpers.md) w sekcjach MACROS i Globals w **dokumentacji MFC**.

`CMap` przesłania [CObject:: serializacji](../../mfc/reference/cobject-class.md#serialize) , aby obsługiwać serializację i zatopienie swoich elementów. Jeśli mapa jest przechowywana w archiwum przy użyciu `Serialize` , każdy element mapy jest z kolei serializowany. Domyślna implementacja `SerializeElements` funkcji pomocnika jest zapisem bitowym. Aby uzyskać informacje o serializacji elementów kolekcji wskaźników pochodnych od `CObject` lub innych typów zdefiniowanych przez użytkownika, zobacz [How to: Make a Type-Safe Collection](../../mfc/how-to-make-a-type-safe-collection.md).

Jeśli potrzebujesz zrzutu diagnostycznego poszczególnych elementów z mapy (klucze i wartości), musisz ustawić głębokość kontekstu zrzutu na 1 lub większą.

Po `CMap` usunięciu obiektu lub po usunięciu jego elementów klucze i wartości są usuwane.

Klasa pochodna klasy map jest podobna do pochodnej listy. Zapoznaj się z [kolekcjami](../../mfc/collections.md) artykułów, aby poznać sposób wyprowadzania klasy listy specjalnego przeznaczenia.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

`CMap`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxtempl. h

## <a name="cmapcmap"></a><a name="cmap"></a> CMap::CMap

Konstruuje pustą mapę.

```
CMap(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>Parametry

*nBlockSize*<br/>
Określa stopień szczegółowości alokacji pamięci na potrzeby rozszerzania mapy.

### <a name="remarks"></a>Uwagi

Gdy mapa zostanie powiększona, pamięć jest przypisana w jednostkach wpisów *nBlockSize* .

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCCollections#56](../../mfc/codesnippet/cpp/cmap-class_1.cpp)]

## <a name="cmapcpair"></a><a name="cpair"></a> CMap::CPair

Zawiera wartość klucza i wartość skojarzonego obiektu.

### <a name="remarks"></a>Uwagi

Jest to struktura zagnieżdżona w klasie [CMAP](../../mfc/reference/cmap-class.md).

Struktura składa się z dwóch pól:

- `key` Rzeczywista wartość typu klucza.

- `value` Wartość skojarzonego obiektu.

Służy do przechowywania wartości zwracanych z [CMAP::P Lookup](#plookup), [CMAP::P getfirstassoc](#pgetfirstassoc)i [CMAP::P GetNextAssoc](#pgetnextassoc).

### <a name="example"></a>Przykład

Aby zapoznać się z przykładem użycia, zobacz przykład dla [CMAP::P Lookup](#plookup).

## <a name="cmapgetcount"></a><a name="getcount"></a> CMap:: GetCount

Pobiera liczbę elementów na mapie.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Wartość zwracana

Liczba elementów.

### <a name="example"></a>Przykład

Zobacz przykład dla [CMAP:: Lookup](#lookup).

## <a name="cmapgethashtablesize"></a><a name="gethashtablesize"></a> CMap::GetHashTableSize

Określa liczbę elementów w tabeli skrótów dla mapy.

```
UINT GetHashTableSize() const;
```

### <a name="return-value"></a>Wartość zwracana

Liczba elementów w tabeli skrótów.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCCollections#57](../../mfc/codesnippet/cpp/cmap-class_2.cpp)]

## <a name="cmapgetnextassoc"></a><a name="getnextassoc"></a> CMap::GetNextAssoc

Pobiera element mapy w `rNextPosition` , a następnie aktualizuje, `rNextPosition` Aby odwołać się do następnego elementu na mapie.

```cpp
void GetNextAssoc(
    POSITION& rNextPosition,
    KEY& rKey,
    VALUE& rValue) const;
```

### <a name="parameters"></a>Parametry

*rNextPosition*<br/>
Określa odwołanie do wartości pozycji zwróconej przez poprzednie `GetNextAssoc` lub `GetStartPosition` wywołanie.

*GŁÓWNYCH*<br/>
Parametr szablonu określający typ klucza mapy.

*rKey*<br/>
Określa zwracany klucz pobranego elementu.

*VALUE*<br/>
Parametr szablonu określający typ wartości mapy.

*rValue*<br/>
Określa zwróconą wartość pobranego elementu.

### <a name="remarks"></a>Uwagi

Ta funkcja jest najbardziej przydatna do iterowania przez wszystkie elementy na mapie. Należy zauważyć, że sekwencja położenia nie musi być taka sama jak sekwencja wartości klucza.

Jeśli pobrany element jest ostatnim na mapie, Nowa wartość *rNextPosition* jest ustawiona na wartość null.

### <a name="example"></a>Przykład

Zobacz przykład dla [CMAP:: SetAt](#setat).

## <a name="cmapgetsize"></a><a name="getsize"></a> CMap:: GetSize

Zwraca liczbę elementów mapy.

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>Wartość zwracana

Liczba elementów na mapie.

### <a name="remarks"></a>Uwagi

Wywołaj tę metodę, aby pobrać liczbę elementów na mapie.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCCollections#58](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]

## <a name="cmapgetstartposition"></a><a name="getstartposition"></a> CMap::GetStartPosition

Uruchamia iterację mapy przez zwrócenie wartości pozycji, która może zostać przeniesiona do `GetNextAssoc` wywołania.

```
POSITION GetStartPosition() const;
```

### <a name="return-value"></a>Wartość zwracana

Wartość pozycji wskazująca na pozycję początkową dla iteracji mapy; lub wartość NULL, jeśli mapa jest pusta.

### <a name="remarks"></a>Uwagi

Sekwencja iteracji nie jest przewidywalna; w związku z tym "pierwszy element w mapie" nie ma specjalnego znaczenia.

### <a name="example"></a>Przykład

Zobacz przykład dla [CMAP:: SetAt](#setat).

## <a name="cmapinithashtable"></a><a name="inithashtable"></a> CMap::InitHashTable

Inicjuje tablicę skrótów.

```cpp
void InitHashTable(UINT hashSize, BOOL  bAllocNow = TRUE);
```

### <a name="parameters"></a>Parametry

*hashSize*<br/>
Liczba wpisów w tabeli skrótów.

*bAllocNow*<br/>
W przypadku wartości TRUE przypisuje tabelę skrótów po inicjacji; w przeciwnym razie tabela jest przydzielenia w razie konieczności.

### <a name="remarks"></a>Uwagi

W celu uzyskania najlepszej wydajności rozmiar tabeli skrótów powinien być liczbą główną. Aby zminimalizować kolizje, rozmiar powinien być w przybliżeniu 20% większy niż największy przewidywany zestaw danych.

### <a name="example"></a>Przykład

Zobacz przykład dla [CMAP:: Lookup](#lookup).

## <a name="cmapisempty"></a><a name="isempty"></a> CMap:: IsEmpty

Określa, czy mapa jest pusta.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Wartość zwracana

Różne od zera, jeśli ta mapa nie zawiera żadnych elementów; w przeciwnym razie 0.

### <a name="example"></a>Przykład

Zobacz przykład dla [CMAP::](#removeall)No.

## <a name="cmaplookup"></a><a name="lookup"></a> CMap:: Lookup

Wyszukuje wartość zamapowane na dany klucz.

```
BOOL Lookup(ARG_KEY key, VALUE& rValue) const;
```

### <a name="parameters"></a>Parametry

*ARG_KEY*<br/>
Parametr szablonu określający typ wartości *klucza* .

*głównych*<br/>
Określa klucz, który identyfikuje element, który ma zostać wyszukany.

*VALUE*<br/>
Określa typ wartości do wyszukania.

*rValue*<br/>
Odbiera wartość wyszukiwania.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli element został znaleziony; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

`Lookup` używa algorytmu wyznaczania wartości skrótu, aby szybko znaleźć element mapy z kluczem, który dokładnie pasuje do danego klucza.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCCollections#58](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]

## <a name="cmapoperator--"></a><a name="operator_at"></a> CMap:: operator []

Wygodny substytut dla `SetAt` funkcji członkowskiej.

```
VALUE& operator[](arg_key key);
```

### <a name="parameters"></a>Parametry

*VALUE*<br/>
Parametr szablonu określający typ wartości mapy.

*ARG_KEY*<br/>
Parametr szablonu określający typ wartości klucza.

*głównych*<br/>
Klucz służący do pobierania wartości z mapy.

### <a name="remarks"></a>Uwagi

Z tego względu można używać tylko po lewej stronie instrukcji przypisania (l-wartość). Jeśli nie ma elementu mapy o określonym kluczu, zostanie utworzony nowy element.

Nie ma "prawa strona" (r-Value) równoważnej temu operatorowi, ponieważ istnieje możliwość, że klucz może nie zostać znaleziony na mapie. Użyj `Lookup` funkcji członkowskiej do pobierania elementów.

### <a name="example"></a>Przykład

Zobacz przykład dla [CMAP:: Lookup](#lookup).

## <a name="cmappgetfirstassoc"></a><a name="pgetfirstassoc"></a> CMap::P GetFirstAssoc

Zwraca pierwszy wpis obiektu mapy.

```
const CPair* PGetFirstAssoc() const;
CPair* PGetFirstAssoc();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do pierwszego wpisu na mapie; Zobacz [CMAP:: CPair](#cpair). Jeśli mapa nie zawiera żadnych wpisów, wartość jest RÓWNa NULL.

### <a name="remarks"></a>Uwagi

Wywołaj tę funkcję, aby zwrócić wskaźnik do pierwszego elementu w obiekcie mapy.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCCollections#59](../../mfc/codesnippet/cpp/cmap-class_4.cpp)]

## <a name="cmappgetnextassoc"></a><a name="pgetnextassoc"></a> CMap::P GetNextAssoc

Pobiera element mapy wskazywany przez *pAssocRec*.

```
const CPair *PGetNextAssoc(const CPair* pAssocRet) const;

CPair *PGetNextAssoc(const CPair* pAssocRet);
```

### <a name="parameters"></a>Parametry

*pAssocRet*<br/>
Wskazuje na wpis mapy zwrócony przez poprzednie [PGetNextAssoc](#pgetnextassoc) lub [CMAP::P wywołanie getfirstassoc](#pgetfirstassoc) .

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do następnego wpisu na mapie; Zobacz [CMAP:: CPair](#cpair). Jeśli element jest ostatnim na mapie, wartość jest RÓWNa NULL.

### <a name="remarks"></a>Uwagi

Wywołaj tę metodę, aby wykonać iterację wszystkich elementów na mapie. Pobranie pierwszego elementu z wywołaniem `PGetFirstAssoc` , a następnie iteracja przez mapę z kolejnymi wywołaniami do `PGetNextAssoc` .

### <a name="example"></a>Przykład

Zobacz przykład dla [CMAP::P getfirstassoc](#pgetfirstassoc).

## <a name="cmapplookup"></a><a name="plookup"></a> CMap: wyszukiwanie:P

Znajduje wartość zamapowana na dany klucz.

```
const CPair* PLookup(ARG_KEY key) const;
CPair* PLookup(ARG_KEY key);
```

### <a name="parameters"></a>Parametry

*głównych*<br/>
Klucz dla elementu, który ma być wyszukiwany.

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do struktury klucza; Zobacz [CMAP:: CPair](#cpair). Jeśli nie zostanie znalezione dopasowanie, `CMap::PLookup` zwraca wartość null.

### <a name="remarks"></a>Uwagi

Wywołaj tę metodę, aby wyszukać element mapy z kluczem, który dokładnie pasuje do podanego klucza.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCCollections#60](../../mfc/codesnippet/cpp/cmap-class_5.cpp)]

## <a name="cmapremoveall"></a><a name="removeall"></a> CMAP::

Usuwa wszystkie wartości z tej mapy, wywołując globalną funkcję pomocnika `DestructElements` .

```cpp
void RemoveAll();
```

### <a name="remarks"></a>Uwagi

Funkcja działa poprawnie, jeśli mapa jest już pusta.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCCollections#61](../../mfc/codesnippet/cpp/cmap-class_6.cpp)]

## <a name="cmapremovekey"></a><a name="removekey"></a> CMap::RemoveKey

Wyszukuje wpis mapy odpowiadający dostarczonemu kluczowi; następnie, jeśli klucz zostanie znaleziony, usuwa wpis.

```
BOOL RemoveKey(ARG_KEY key);
```

### <a name="parameters"></a>Parametry

*ARG_KEY*<br/>
Parametr szablonu określający typ klucza.

*głównych*<br/>
Klucz dla elementu, który ma zostać usunięty.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, Jeśli wpis został znaleziony i pomyślnie usunięty; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

`DestructElements`Funkcja pomocnika służy do usuwania wpisu.

### <a name="example"></a>Przykład

Zobacz przykład dla [CMAP:: SetAt](#setat).

## <a name="cmapsetat"></a><a name="setat"></a> CMap::SetAt

Podstawowy oznacza Wstawianie elementu na mapie.

```cpp
void SetAt(ARG_KEY key, ARG_VALUE newValue);
```

### <a name="parameters"></a>Parametry

*ARG_KEY*<br/>
Parametr szablonu określający typ parametru *klucza* .

*głównych*<br/>
Określa klucz nowego elementu.

*ARG_VALUE*<br/>
Parametr szablonu określający typ parametru *NewValue* .

*newValue*<br/>
Określa wartość nowego elementu.

### <a name="remarks"></a>Uwagi

Najpierw jest wyszukiwany klucz. Jeśli klucz zostanie znaleziony, oznacza to, że odpowiednia wartość zostanie zmieniona; w przeciwnym razie zostanie utworzona nowa para klucz-wartość.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCCollections#62](../../mfc/codesnippet/cpp/cmap-class_7.cpp)]

## <a name="see-also"></a>Zobacz także

[ZBIERANIE próbek MFC](../../overview/visual-cpp-samples.md)<br/>
[Klasa CObject](../../mfc/reference/cobject-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)

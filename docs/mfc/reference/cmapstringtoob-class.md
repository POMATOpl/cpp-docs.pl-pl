---
description: 'Dowiedz się więcej na temat: Klasa CMapStringToOb'
title: Klasa CMapStringToOb
ms.date: 11/04/2016
f1_keywords:
- CMapStringToOb
- AFXCOLL/CMapStringToOb
- AFXCOLL/CMapStringToOb::CMapStringToOb
- AFXCOLL/CMapStringToOb::GetCount
- AFXCOLL/CMapStringToOb::GetHashTableSize
- AFXCOLL/CMapStringToOb::GetNextAssoc
- AFXCOLL/CMapStringToOb::GetSize
- AFXCOLL/CMapStringToOb::GetStartPosition
- AFXCOLL/CMapStringToOb::HashKey
- AFXCOLL/CMapStringToOb::InitHashTable
- AFXCOLL/CMapStringToOb::IsEmpty
- AFXCOLL/CMapStringToOb::Lookup
- AFXCOLL/CMapStringToOb::LookupKey
- AFXCOLL/CMapStringToOb::RemoveAll
- AFXCOLL/CMapStringToOb::RemoveKey
- AFXCOLL/CMapStringToOb::SetAt
helpviewer_keywords:
- CMapStringToOb [MFC], CMapStringToOb
- CMapStringToOb [MFC], GetCount
- CMapStringToOb [MFC], GetHashTableSize
- CMapStringToOb [MFC], GetNextAssoc
- CMapStringToOb [MFC], GetSize
- CMapStringToOb [MFC], GetStartPosition
- CMapStringToOb [MFC], HashKey
- CMapStringToOb [MFC], InitHashTable
- CMapStringToOb [MFC], IsEmpty
- CMapStringToOb [MFC], Lookup
- CMapStringToOb [MFC], LookupKey
- CMapStringToOb [MFC], RemoveAll
- CMapStringToOb [MFC], RemoveKey
- CMapStringToOb [MFC], SetAt
ms.assetid: 09653980-b885-4f3a-8594-0aeb7f94c601
ms.openlocfilehash: 9bd5f47fbb85e67784e5bcb50029d9d9e48e5bb4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207868"
---
# <a name="cmapstringtoob-class"></a>Klasa CMapStringToOb

Klasa kolekcji słownika, która mapuje unikatowe `CString` obiekty na `CObject` wskaźniki.

## <a name="syntax"></a>Składnia

```
class CMapStringToOb : public CObject
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMapStringToOb::CMapStringToOb](#cmapstringtoob)|Konstruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMapStringToOb:: GetCount](#getcount)|Zwraca liczbę elementów w tej mapie.|
|[CMapStringToOb::GetHashTableSize](#gethashtablesize)|Określa bieżącą liczbę elementów w tabeli skrótów.|
|[CMapStringToOb::GetNextAssoc](#getnextassoc)|Pobiera następny element do iteracji.|
|[CMapStringToOb:: GetSize](#getsize)|Zwraca liczbę elementów w tej mapie.|
|[CMapStringToOb::GetStartPosition](#getstartposition)|Zwraca pozycję pierwszego elementu.|
|[CMapStringToOb::HashKey](#hashkey)|Oblicza wartość skrótu określonego klucza.|
|[CMapStringToOb::InitHashTable](#inithashtable)|Inicjuje tablicę skrótów.|
|[CMapStringToOb:: IsEmpty](#isempty)|Testuje warunek pustej mapy (nie elementy).|
|[CMapStringToOb:: Lookup](#lookup)|Wyszukuje wskaźnik void na podstawie klucza wskaźnika void. Wartość wskaźnika, a nie jednostka, do której wskazuje, jest używana do porównania klucza.|
|[CMapStringToOb:: LookupKey](#lookupkey)|Zwraca odwołanie do klucza skojarzonego z określoną wartością klucza.|
|[CMapStringToOb::](#removeall)|Usuwa wszystkie elementy z tej mapy.|
|[CMapStringToOb::RemoveKey](#removekey)|Usuwa element określony przez klucz.|
|[CMapStringToOb::SetAt](#setat)|Wstawia element do mapy; Zastępuje istniejący element, jeśli zostanie znaleziony pasujący klucz.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMapStringToOb:: operator \[\]](#operator_at)|Wstawia element do mapy — podstawienia operatora dla `SetAt` .|

## <a name="remarks"></a>Uwagi

Po wstawieniu `CString` -  `CObject*` pary (elementu) do mapy można efektywnie pobrać lub usunąć parę przy użyciu ciągu lub `CString` wartości jako klucza. Możesz również wykonać iterację wszystkich elementów na mapie.

Zmienna typu pozycja jest używana na potrzeby alternatywnego dostępu do wpisów we wszystkich odmianach mapy. Możesz użyć pozycji do "zapamiętać" wpisu i iteracji przez mapę. Można sądzić, że ta Iteracja jest sekwencyjna według wartości klucza; nie jest. Sekwencja pobranych elementów jest nieokreślona.

`CMapStringToOb` zawiera `IMPLEMENT_SERIAL` makro obsługujące serializację i zatopienie swoich elementów. Każdy element jest serializowany, jeśli mapa jest przechowywana w archiwum, przy użyciu przeciążonego operatora wstawiania ( **<<** ) lub `Serialize` funkcji członkowskiej.

Jeśli potrzebujesz zrzutu diagnostycznego poszczególnych elementów na mapie ( `CString` wartość i `CObject` zawartość), musisz ustawić głębokość kontekstu zrzutu na 1 lub większą.

Po `CMapStringToOb` usunięciu obiektu lub po usunięciu jego elementów `CString` obiekty i `CObject` wskaźniki są usuwane. Obiekty, do których odwołuje się `CObject` wskaźnik, nie są niszczone.

Klasa pochodna klasy map jest podobna do pochodnej listy. Zapoznaj się z [kolekcjami](../../mfc/collections.md) artykułów, aby poznać sposób wyprowadzania klasy listy specjalnego przeznaczenia.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

`CMapStringToOb`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxcoll. h

## <a name="cmapstringtoobcmapstringtoob"></a><a name="cmapstringtoob"></a> CMapStringToOb::CMapStringToOb

Konstruuje pustą `CString` `CObject*` mapę.

```
CMapStringToOb(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>Parametry

*nBlockSize*<br/>
Określa stopień szczegółowości alokacji pamięci na potrzeby rozszerzania mapy.

### <a name="remarks"></a>Uwagi

Gdy mapa zostanie powiększona, pamięć jest przypisana w jednostkach wpisów *nBlockSize* .

W poniższej tabeli przedstawiono inne funkcje członkowskie, które są podobne do `CMapStringToOb:: CMapStringToOb` .

|Klasa|Funkcja elementów członkowskich|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**CMapPtrToPtr (INT_PTR** `nBlockSize` **= 10);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**CMapPtrToWord (INT_PTR** `nBlockSize` **= 10);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**CMapStringToPtr (INT_PTR** `nBlockSize` **= 10);**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**CMapStringToString (INT_PTR** `nBlockSize` **= 10);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**CMapWordToOb (INT_PTR** `nBlockSize` **= 10);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**MapWordToPtr (INT_PTR** `nBlockSize` **= 10);**|

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCCollections#63](../../mfc/codesnippet/cpp/cmapstringtoob-class_1.cpp)]

Zobacz [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) , aby zapoznać się z listą `CAge` klasy używanej we wszystkich przykładach kolekcji.

## <a name="cmapstringtoobgetcount"></a><a name="getcount"></a> CMapStringToOb:: GetCount

Określa, ile elementów znajduje się na mapie.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Wartość zwracana

Liczba elementów w tej mapie.

### <a name="remarks"></a>Uwagi

W poniższej tabeli przedstawiono inne funkcje członkowskie, które są podobne do `CMapStringToOb::GetCount` .

|Klasa|Funkcja elementów członkowskich|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**INT_PTR GetCount () const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**INT_PTR GetCount () const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**INT_PTR GetCount () const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**INT_PTR GetCount () const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**INT_PTR GetCount () const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**INT_PTR GetCount () const;**|

### <a name="example"></a>Przykład

Zobacz [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) , aby zapoznać się z listą `CAge` klasy używanej we wszystkich przykładach kolekcji.

[!code-cpp[NVC_MFCCollections#64](../../mfc/codesnippet/cpp/cmapstringtoob-class_2.cpp)]

## <a name="cmapstringtoobgethashtablesize"></a><a name="gethashtablesize"></a> CMapStringToOb::GetHashTableSize

Określa bieżącą liczbę elementów w tabeli skrótów.

```
UINT GetHashTableSize() const;
```

### <a name="return-value"></a>Wartość zwracana

Zwraca liczbę elementów w tabeli skrótów.

### <a name="remarks"></a>Uwagi

W poniższej tabeli przedstawiono inne funkcje członkowskie, które są podobne do `CMapStringToOb::GetHashTableSize` .

|Klasa|Funkcja elementów członkowskich|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**UINT GetHashTableSize () const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**UINT GetHashTableSize () const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**UINT GetHashTableSize () const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**UINT GetHashTableSize () const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**UINT GetHashTableSize () const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**UINT GetHashTableSize () const;**|

## <a name="cmapstringtoobgetnextassoc"></a><a name="getnextassoc"></a> CMapStringToOb::GetNextAssoc

Pobiera element mapy w *rNextPosition*, a następnie aktualizuje *rNextPosition* w celu odwoływania się do następnego elementu na mapie.

```cpp
void GetNextAssoc(
    POSITION& rNextPosition,
    CString& rKey,
    CObject*& rValue) const;
```

### <a name="parameters"></a>Parametry

*rNextPosition*<br/>
Określa odwołanie do wartości pozycji zwróconej przez poprzednie `GetNextAssoc` lub `GetStartPosition` wywołanie.

*rKey*<br/>
Określa zwracany klucz pobranego elementu (ciąg).

*rValue*<br/>
Określa zwróconą wartość pobranego elementu ( `CObject` wskaźnik). Aby uzyskać więcej informacji o tym parametrze, zobacz uwagi.

### <a name="remarks"></a>Uwagi

Ta funkcja jest najbardziej przydatna do iterowania przez wszystkie elementy na mapie. Należy zauważyć, że sekwencja położenia nie musi być taka sama jak sekwencja wartości klucza.

Jeśli pobrany element jest ostatnim na mapie, Nowa wartość *rNextPosition* jest ustawiona na wartość null.

Dla parametru *rValue* upewnij się, że typ obiektu jest rzutowany na **CObject \* &**, co jest wymagane przez kompilator, jak pokazano w następującym przykładzie:

[!code-cpp[NVC_MFCCollections#65](../../mfc/codesnippet/cpp/cmapstringtoob-class_3.cpp)]

To nie jest prawdziwe `GetNextAssoc` w przypadku map opartych na szablonach.

W poniższej tabeli przedstawiono inne funkcje członkowskie, które są podobne do `CMapStringToOb::GetNextAssoc` .

|Klasa|Funkcja elementów członkowskich|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void GetNextAssoc (pozycja&** *rNextPosition* **, void \* &** *rKey* **, void \* &** *rValue* **) const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void GetNextAssoc (pozycja&** *rNextPosition* **, void \* &** *rKey* **, Word&** *rValue* **) const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void GetNextAssoc (pozycja&** *rNextPosition* **, CString&** *rKey* **, void \* &** *rValue* **) const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void GetNextAssoc (pozycja&** *rNextPosition* **, CString&** *rKey* **, CString&** *rValue* **) const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void GetNextAssoc (pozycja&** *rNextPosition* **, Word&** *rKey* **, CObject \* &** *rValue* **) const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void GetNextAssoc (pozycja&** *rNextPosition* **, Word&** *rKey* **, void \* &** *rValue* **) const;**|

### <a name="example"></a>Przykład

Zobacz [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) , aby zapoznać się z listą `CAge` klasy używanej we wszystkich przykładach kolekcji.

[!code-cpp[NVC_MFCCollections#66](../../mfc/codesnippet/cpp/cmapstringtoob-class_4.cpp)]

Wyniki z tego programu są następujące:

```Output
Lisa : a CAge at $4724 11
Marge : a CAge at $47A8 35
Homer : a CAge at $4766 36
Bart : a CAge at $45D4 13
```

## <a name="cmapstringtoobgetsize"></a><a name="getsize"></a> CMapStringToOb:: GetSize

Zwraca liczbę elementów mapy.

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>Wartość zwracana

Liczba elementów na mapie.

### <a name="remarks"></a>Uwagi

Wywołaj tę metodę, aby pobrać liczbę elementów na mapie.

W poniższej tabeli przedstawiono inne funkcje członkowskie, które są podobne do `CMapStringToOb::GetSize` .

|Klasa|Funkcja elementów członkowskich|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**INT_PTR GetSize () const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**INT_PTR GetSize () const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**INT_PTR GetSize () const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**INT_PTR GetSize () const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**INT_PTR GetSize () const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**INT_PTR GetSize () const;**|

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCCollections#67](../../mfc/codesnippet/cpp/cmapstringtoob-class_5.cpp)]

## <a name="cmapstringtoobgetstartposition"></a><a name="getstartposition"></a> CMapStringToOb::GetStartPosition

Uruchamia iterację mapy przez zwrócenie wartości pozycji, która może zostać przeniesiona do `GetNextAssoc` wywołania.

```
POSITION GetStartPosition() const;
```

### <a name="return-value"></a>Wartość zwracana

Wartość pozycji wskazująca na pozycję początkową dla iteracji mapy; lub wartość NULL, jeśli mapa jest pusta.

### <a name="remarks"></a>Uwagi

Sekwencja iteracji nie jest przewidywalna; w związku z tym "pierwszy element w mapie" nie ma specjalnego znaczenia.

W poniższej tabeli przedstawiono inne funkcje członkowskie, które są podobne do `CMapStringToOb::GetStartPosition` .

|Klasa|Funkcja elementów członkowskich|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**POSITION GetStartPosition () const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**POSITION GetStartPosition () const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**POSITION GetStartPosition () const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**POSITION GetStartPosition () const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**POSITION GetStartPosition () const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**POSITION GetStartPosition () const;**|

### <a name="example"></a>Przykład

Zobacz przykład dla [CMapStringToOb:: GetNextAssoc](#getnextassoc).

## <a name="cmapstringtoobhashkey"></a><a name="hashkey"></a> CMapStringToOb::HashKey

Oblicza wartość skrótu określonego klucza.

```
UINT HashKey(LPCTSTR key) const;
```

### <a name="parameters"></a>Parametry

*głównych*<br/>
Klucz, dla którego ma zostać obliczona wartość skrótu.

### <a name="return-value"></a>Wartość zwracana

Wartość skrótu klucza

### <a name="remarks"></a>Uwagi

W poniższej tabeli przedstawiono inne funkcje członkowskie, które są podobne do `CMapStringToOb::HashKey` .

|Klasa|Funkcja elementów członkowskich|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**Uint HashKey (void** <strong>\*</strong> `key` **) const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**Uint HashKey (void** <strong>\*</strong> `key` **) const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**Uint HashKey (LPCTSTR** `key` **) const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**Uint HashKey (LPCTSTR** `key` **) const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**Uint HashKey (słowo** `key` **) const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**Uint HashKey (słowo** `key` **) const;**|

## <a name="cmapstringtoobinithashtable"></a><a name="inithashtable"></a> CMapStringToOb::InitHashTable

Inicjuje tablicę skrótów.

```cpp
void InitHashTable(
    UINT hashSize,
    BOOL bAllocNow = TRUE);
```

### <a name="parameters"></a>Parametry

*hashSize*<br/>
Liczba wpisów w tabeli skrótów.

*bAllocNow*<br/>
W przypadku wartości TRUE przypisuje tabelę skrótów po inicjacji; w przeciwnym razie tabela jest przydzielenia w razie konieczności.

### <a name="remarks"></a>Uwagi

W celu uzyskania najlepszej wydajności rozmiar tabeli skrótów powinien być liczbą główną. Aby zminimalizować kolizje, rozmiar powinien być w przybliżeniu 20% większy niż największy przewidywany zestaw danych.

W poniższej tabeli przedstawiono inne funkcje członkowskie, które są podobne do `CMapStringToOb::InitHashTable` .

|Klasa|Funkcja elementów członkowskich|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void InitHashTable (uint** `hashSize` **, bool** `bAllocNow` **= true);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void InitHashTable (uint** `hashSize` **, bool** `bAllocNow` **= true);**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void InitHashTable (uint** `hashSize` **, bool** `bAllocNow` **= true);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void InitHashTable (uint** `hashSize` **, bool** `bAllocNow` **= true);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void InitHashTable (uint** `hashSize` **, bool** `bAllocNow` **= true);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void InitHashTable (uint** `hashSize` **, bool** `bAllocNow` **= true);**|

## <a name="cmapstringtoobisempty"></a><a name="isempty"></a> CMapStringToOb:: IsEmpty

Określa, czy mapa jest pusta.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Wartość zwracana

Różne od zera, jeśli ta mapa nie zawiera żadnych elementów; w przeciwnym razie 0.

### <a name="example"></a>Przykład

Zobacz [przykład dla mnie](#removeall).

### <a name="remarks"></a>Uwagi

W poniższej tabeli przedstawiono inne funkcje członkowskie, które są podobne do **CMapStringToOb:: IsEmpty**.

|Klasa|Funkcja elementów członkowskich|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL IsEmpty () const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**BOOL IsEmpty () const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL IsEmpty () const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL IsEmpty () const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**BOOL IsEmpty () const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**BOOL IsEmpty () const;**|

## <a name="cmapstringtooblookup"></a><a name="lookup"></a> CMapStringToOb:: Lookup

Zwraca `CObject` wskaźnik na podstawie `CString` wartości.

```
BOOL Lookup(
    LPCTSTR key,
    CObject*& rValue) const;
```

### <a name="parameters"></a>Parametry

*głównych*<br/>
Określa klucz ciągu identyfikujący element, który ma zostać wyszukany.

*rValue*<br/>
Określa wartość zwracaną z elementu, który ma być wyszukiwany.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli element został znaleziony; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

`Lookup` używa algorytmu wyznaczania wartości skrótu, aby szybko znaleźć element mapy z kluczem, który pasuje dokładnie ( `CString` wartość).

W poniższej tabeli przedstawiono inne funkcje członkowskie, które są podobne do `CMapStringToOb::LookUp` .

|Klasa|Funkcja elementów członkowskich|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**Wyszukiwanie bool (void** <strong>\*</strong> `key` **, void \* &** `rValue` **) const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**Wyszukiwanie bool (void** <strong>\*</strong> `key` **, WORD&** `rValue` **) const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**Wyszukiwanie bool (LPCTSTR** `key` **, void \* &** `rValue` **) const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**Wyszukiwanie bool (LPCTSTR** `key` **, CString&** `rValue` **) const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**Odnośnik bool (Word** `key` **, CObject \* &** `rValue` **) const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**Odnośnik bool (Word** `key` **, void \* &** `rValue` **) const;**|

### <a name="example"></a>Przykład

Zobacz [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) , aby zapoznać się z listą `CAge` klasy używanej we wszystkich przykładach kolekcji.

[!code-cpp[NVC_MFCCollections#68](../../mfc/codesnippet/cpp/cmapstringtoob-class_6.cpp)]

## <a name="cmapstringtooblookupkey"></a><a name="lookupkey"></a> CMapStringToOb:: LookupKey

Zwraca odwołanie do klucza skojarzonego z określoną wartością klucza.

```
BOOL LookupKey(
    LPCTSTR key,
    LPCTSTR& rKey) const;
```

### <a name="parameters"></a>Parametry

*głównych*<br/>
Określa klucz ciągu identyfikujący element, który ma zostać wyszukany.

*rKey*<br/>
Odwołanie do skojarzonego klucza.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli klucz został znaleziony; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Użycie odwołania do klucza jest niebezpieczne, jeśli jest używane po usunięciu skojarzonego elementu z mapy lub po zniszczeniu mapy.

W poniższej tabeli przedstawiono inne funkcje członkowskie, które są podobne do `CMapStringToOb:: LookupKey` .

|Klasa|Funkcja elementów członkowskich|
|-----------|---------------------|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**Bool LookupKey (LPCTSTR** `key` **, LPCTSTR&** `rKey` **) const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**Bool LookupKey (LPCTSTR** `key` **, LPCTSTR&** `rKey` **) const;**|

## <a name="cmapstringtooboperator--"></a><a name="operator_at"></a> CMapStringToOb:: operator []

Wygodny substytut dla `SetAt` funkcji członkowskiej.

```
CObject*& operator[ ](lpctstr key);
```

### <a name="return-value"></a>Wartość zwracana

Odwołanie do wskaźnika do `CObject` obiektu; lub wartość null, jeśli mapa jest pusta lub *klucz* znajduje się poza zakresem.

### <a name="remarks"></a>Uwagi

Z tego względu można używać tylko po lewej stronie instrukcji przypisania (l-wartość). Jeśli nie ma elementu mapy o określonym kluczu, zostanie utworzony nowy element.

Nie ma "prawa strona" (r-Value) równoważnej temu operatorowi, ponieważ istnieje możliwość, że klucz może nie zostać znaleziony na mapie. Użyj `Lookup` funkcji członkowskiej do pobierania elementów.

W poniższej tabeli przedstawiono inne funkcje członkowskie, które są podobne do `CMapStringToOb::operator []` .

|Klasa|Funkcja elementów członkowskich|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|<strong> \* operator void& \[ ] (void \*</strong> `key` **\) ;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**Słowo& — operator \[ ] (void** <strong>\*</strong> `key` **\);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**\* operator void& \[ ] (LPCTSTR** `key` **\) ;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**CString — operator& \[ ] (LPCTSTR** `key` **\);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**CObject — \* operator& \[ ] (Word** `key` **\) ;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**\* operator void& \[ ] (Word** `key` **\) ;**|

### <a name="example"></a>Przykład

Zobacz [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) , aby zapoznać się z listą `CAge` klasy używanej we wszystkich przykładach kolekcji.

[!code-cpp[NVC_MFCCollections#72](../../mfc/codesnippet/cpp/cmapstringtoob-class_7.cpp)]

Wyniki z tego programu są następujące:

```Output
Operator [] example: A CMapStringToOb with 2 elements
[Lisa] = a CAge at $4A02 11
[Bart] = a CAge at $497E 13
```

## <a name="cmapstringtoobremoveall"></a><a name="removeall"></a> CMapStringToOb::

Usuwa wszystkie elementy z tej mapy i niszczy `CString` obiekty kluczowe.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>Uwagi

`CObject`Obiekty, do których odwołuje się każdy klucz, nie są niszczone. `RemoveAll`Funkcja może spowodować przecieki pamięci, jeśli nie masz pewność, że obiekty, do których występują odwołania, `CObject` są niszczone.

Funkcja działa poprawnie, jeśli mapa jest już pusta.

W poniższej tabeli przedstawiono inne funkcje członkowskie, które są podobne do `CMapStringToOb::RemoveAll` .

|Klasa|Funkcja elementów członkowskich|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void No();**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void No();**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void No();**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void No();**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void No();**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void No();**|

### <a name="example"></a>Przykład

Zobacz [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) , aby zapoznać się z listą `CAge` klasy używanej we wszystkich przykładach kolekcji.

[!code-cpp[NVC_MFCCollections#69](../../mfc/codesnippet/cpp/cmapstringtoob-class_8.cpp)]

## <a name="cmapstringtoobremovekey"></a><a name="removekey"></a> CMapStringToOb::RemoveKey

Wyszukuje wpis mapy odpowiadający dostarczonemu kluczowi; następnie, jeśli klucz zostanie znaleziony, usuwa wpis.

```
BOOL RemoveKey(LPCTSTR key);
```

### <a name="parameters"></a>Parametry

*głównych*<br/>
Określa ciąg używany do wyszukiwania map.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, Jeśli wpis został znaleziony i pomyślnie usunięty; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Może to spowodować przecieki pamięci, jeśli `CObject` obiekt nie został usunięty w innym miejscu.

W poniższej tabeli przedstawiono inne funkcje członkowskie, które są podobne do `CMapStringToOb::RemoveKey` .

|Klasa|Funkcja elementów członkowskich|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**Bool RemoveKey (void** <strong>\*</strong> `key` **);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**Bool RemoveKey (void** <strong>\*</strong> `key` **);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**Bool RemoveKey (LPCTSTR** `key` **);**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**Bool RemoveKey (LPCTSTR** `key` **);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**Bool RemoveKey (słowo** `key` **);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**Bool RemoveKey (słowo** `key` **);**|

### <a name="example"></a>Przykład

Zobacz [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) , aby zapoznać się z listą `CAge` klasy używanej we wszystkich przykładach kolekcji.

[!code-cpp[NVC_MFCCollections#70](../../mfc/codesnippet/cpp/cmapstringtoob-class_9.cpp)]

Wyniki z tego programu są następujące:

```Output
RemoveKey example: A CMapStringToOb with 3 elements
[Marge] = a CAge at $49A0 35
[Homer] = a CAge at $495E 36
[Bart] = a CAge at $4634 13
```

## <a name="cmapstringtoobsetat"></a><a name="setat"></a> CMapStringToOb::SetAt

Podstawowy oznacza Wstawianie elementu na mapie.

```cpp
void SetAt(
    LPCTSTR key,
    CObject* newValue);
```

### <a name="parameters"></a>Parametry

*głównych*<br/>
Określa ciąg, który jest kluczem nowego elementu.

*newValue*<br/>
Określa `CObject` wskaźnik, który jest wartością nowego elementu.

### <a name="remarks"></a>Uwagi

Najpierw jest wyszukiwany klucz. Jeśli klucz zostanie znaleziony, oznacza to, że odpowiednia wartość zostanie zmieniona; w przeciwnym razie zostanie utworzony nowy element klucz-wartość.

W poniższej tabeli przedstawiono inne funkcje członkowskie, które są podobne do `CMapStringToOb::SetAt` .

|Klasa|Funkcja elementów członkowskich|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void SetAt (void** <strong>\*</strong> `key` **, void** <strong>\*</strong> `newValue` **);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void SetAt (void** <strong>\*</strong> `key` **, Word** `newValue` **);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void SetAt (LPCTSTR** `key` **, void** <strong>\*</strong> `newValue` **);**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void SetAt (LPCTSTR** `key` **, LPCTSTR** `newValue` **);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void SetAt (Word** `key` **, CObject** <strong>\*</strong> `newValue` **);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void SetAt (Word** `key` **, void** <strong>\*</strong> `newValue` **);**|

### <a name="example"></a>Przykład

Zobacz [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) , aby zapoznać się z listą `CAge` klasy używanej we wszystkich przykładach kolekcji.

[!code-cpp[NVC_MFCCollections#71](../../mfc/codesnippet/cpp/cmapstringtoob-class_10.cpp)]

Wyniki z tego programu są następujące:

```Output
before Lisa's birthday: A CMapStringToOb with 2 elements
[Lisa] = a CAge at $493C 11
[Bart] = a CAge at $4654 13
after Lisa's birthday: A CMapStringToOb with 2 elements
[Lisa] = a CAge at $49C0 12
[Bart] = a CAge at $4654 13
```

## <a name="see-also"></a>Zobacz też

[Klasa CObject](../../mfc/reference/cobject-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)<br/>
[Klasa CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)<br/>
[Klasa CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)<br/>
[Klasa CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)<br/>
[Klasa CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)<br/>
[Klasa CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)

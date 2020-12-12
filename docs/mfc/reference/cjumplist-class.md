---
description: 'Dowiedz się więcej na temat: Klasa CJumpList'
title: Klasa CJumpList
ms.date: 03/27/2019
f1_keywords:
- CJumpList
- AFXADV/CJumpList
- AFXADV/CJumpList::CJumpList
- AFXADV/CJumpList::AbortList
- AFXADV/CJumpList::AddDestination
- AFXADV/CJumpList::AddKnownCategory
- AFXADV/CJumpList::AddTask
- AFXADV/CJumpList::AddTasks
- AFXADV/CJumpList::AddTaskSeparator
- AFXADV/CJumpList::ClearAll
- AFXADV/CJumpList::ClearAllDestinations
- AFXADV/CJumpList::CommitList
- AFXADV/CJumpList::GetDestinationList
- AFXADV/CJumpList::GetMaxSlots
- AFXADV/CJumpList::GetRemovedItems
- AFXADV/CJumpList::InitializeList
- AFXADV/CJumpList::SetAppID
helpviewer_keywords:
- CJumpList [MFC], CJumpList
- CJumpList [MFC], AbortList
- CJumpList [MFC], AddDestination
- CJumpList [MFC], AddKnownCategory
- CJumpList [MFC], AddTask
- CJumpList [MFC], AddTasks
- CJumpList [MFC], AddTaskSeparator
- CJumpList [MFC], ClearAll
- CJumpList [MFC], ClearAllDestinations
- CJumpList [MFC], CommitList
- CJumpList [MFC], GetDestinationList
- CJumpList [MFC], GetMaxSlots
- CJumpList [MFC], GetRemovedItems
- CJumpList [MFC], InitializeList
- CJumpList [MFC], SetAppID
ms.assetid: d364d27e-f512-4b12-9872-c2a17c78ab1f
ms.openlocfilehash: 07e896c5b3a205a44850d45dcc4876103a48f2fa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236909"
---
# <a name="cjumplist-class"></a>Klasa CJumpList

A `CJumpList` to lista skrótów ujawnionych po kliknięciu prawym przyciskiem myszy ikony na pasku zadań.

## <a name="syntax"></a>Składnia

```
class CJumpList;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CJumpList::CJumpList](#cjumplist)|Konstruuje `CJumpList` obiekt.|
|[CJumpList:: ~ CJumpList](#_dtorcjumplist)|Niszczy `CJumpList` obiekt.|

|Nazwa|Opis|
|----------|-----------------|
|[CJumpList::AbortList](#abortlist)|Przerywa transakcję tworzenia listy bez zatwierdzania.|
|[CJumpList:: adddestination](#adddestination)|Przeciążone. Dodaje miejsce docelowe do listy.|
|[CJumpList::AddKnownCategory](#addknowncategory)|Dołącza znaną kategorię do listy.|
|[CJumpList:: AddTask](#addtask)|Przeciążone. Dodaje elementy do kategorii zadania kanoniczne.|
|[CJumpList:: addtasks](#addtasks)|Dodaje elementy do kategorii zadania kanoniczne.|
|[CJumpList::AddTaskSeparator](#addtaskseparator)|Dodaje separator między zadaniami.|
|[CJumpList:: ClearAll](#clearall)|Usuwa wszystkie zadania i miejsca docelowe, które zostały dodane do bieżącego wystąpienia `CJumpList` .|
|[CJumpList::ClearAllDestinations](#clearalldestinations)|Usuwa wszystkie miejsca docelowe, które zostały dodane do bieżącego wystąpienia `CJumpList` .|
|[CJumpList::CommitList](#commitlist)|Zamyka transakcję tworzenia listy i zatwierdza zgłoszoną listę do skojarzonego magazynu (rejestr w tym przypadku).|
|[CJumpList::GetDestinationList](#getdestinationlist)|Pobiera wskaźnik interfejsu do listy docelowej.|
|[CJumpList::GetMaxSlots](#getmaxslots)|Pobiera maksymalną liczbę elementów, włącznie z nagłówkami kategorii, które mogą być wyświetlane w menu docelowym aplikacji wywołującej.|
|[CJumpList::GetRemovedItems](#getremoveditems)|Zwraca tablicę elementów reprezentujących usunięte miejsca docelowe.|
|[CJumpList::InitializeList](#initializelist)|Rozpoczyna transakcję tworzenia listy.|
|[CJumpList:: setappid](#setappid)|Ustawia identyfikator modelu użytkownika aplikacji dla listy, który zostanie skompilowany.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CJumpList](../../mfc/reference/cjumplist-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxadv. h

## <a name="cjumplistcjumplist"></a><a name="_dtorcjumplist"></a> CJumpList:: ~ CJumpList

Niszczy `CJumpList` obiekt.

```
~CJumpList();
```

## <a name="cjumplistabortlist"></a><a name="abortlist"></a> CJumpList::AbortList

Przerywa transakcję tworzenia listy bez zatwierdzania.

```cpp
void AbortList();
```

### <a name="remarks"></a>Uwagi

Wywołanie tej metody ma taki sam skutek jak niszczenie `CJumpList` bez wywoływania `CommitList` .

## <a name="cjumplistadddestination"></a><a name="adddestination"></a> CJumpList:: adddestination

Dodaje miejsce docelowe do listy.

```
BOOL AddDestination(
    LPCTSTR lpcszCategoryName,
    LPCTSTR strDestinationPath);

BOOL AddDestination(
    LPCTSTR strCategoryName,
    IShellItem* pShellItem);

BOOL AddDestination(
    LPCTSTR strCategoryName,
    IShellLink* pShellLink);
```

### <a name="parameters"></a>Parametry

*lpcszCategoryName*<br/>
Określa nazwę kategorii. Jeśli określona Kategoria nie istnieje, zostanie utworzona.

*strDestinationPath*<br/>
Określa ścieżkę do pliku docelowego.

*strCategoryName*<br/>
Określa nazwę kategorii. Jeśli określona Kategoria nie istnieje, zostanie utworzona.

*pShellItem*<br/>
Określa element powłoki reprezentujący dodaną lokalizację docelową.

*pShellLink*<br/>
Określa link powłoki reprezentujący dodaną lokalizację docelową.

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

Wystąpienie `CJumpList` wewnętrznie sumuje dodane miejsca docelowe, a następnie zatwierdza je w `CommitList` .

## <a name="cjumplistaddknowncategory"></a><a name="addknowncategory"></a> CJumpList::AddKnownCategory

Dołącza znaną kategorię do listy.

```
BOOL AddKnownCategory(KNOWNDESTCATEGORY category);
```

### <a name="parameters"></a>Parametry

*kategorii*<br/>
Określa znany typ kategorii. Może to być KDC_RECENT lub KDC_KNOWN.

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

Znane kategorie to często używane i niedawne kategorie, które będą automatycznie obliczane dla każdej aplikacji, która używa `SHAddToRecentDocs` (lub pośrednio ją wykorzystuje, gdy powłoka wywoła ją w imieniu aplikacji w niektórych scenariuszach).

## <a name="cjumplistaddtask"></a><a name="addtask"></a> CJumpList:: AddTask

Dodaje elementy do kategorii zadania kanoniczne.

```
BOOL AddTask(
    LPCTSTR strTargetExecutablePath,
    LPCTSTR strCommandLineArgs,
    LPCTSTR strTitle,
    LPCTSTR strIconLocation,
    int iIconIndex);

BOOL AddTask(IShellLink* pShellLink);
```

### <a name="parameters"></a>Parametry

*strTargetExecutablePath*<br/>
Określa ścieżkę zadania docelowego.

*strCommandLineArgs*<br/>
Określa argumenty wiersza polecenia pliku wykonywalnego określonego przez *strTargetExecutablePath*.

*strTitle*<br/>
Nazwa zadania, która będzie wyświetlana na liście docelowej.

*strIconLocation*<br/>
Lokalizacja ikony, która będzie wyświetlana na liście docelowej wraz z tytułem.

*iIconIndex*<br/>
Indeks ikon.

*pShellLink*<br/>
Link powłoki reprezentujący zadanie, które ma zostać dodane.

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

Wystąpienie `CJumpList` gromadzi określone zadania i dodaje je do listy docelowej podczas `CommitList` . Elementy zadań będą wyświetlane w kategorii u dołu menu docelowego aplikacji. Ta kategoria ma pierwszeństwo przed wszystkimi innymi kategoriami, gdy jest wypełniona w interfejsie użytkownika.

## <a name="cjumplistaddtasks"></a><a name="addtasks"></a> CJumpList:: addtasks

Dodaje elementy do kategorii zadania kanoniczne.

```
BOOL AddTasks(IObjectArray* pObjectCollection);
```

### <a name="parameters"></a>Parametry

*pObjectCollection*<br/>
Kolekcja zadań do dodania.

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

Wystąpienie elementu CJumpList gromadzi określone zadania i dodaje je do listy docelowej podczas `CommitList` . Elementy zadań będą wyświetlane w kategorii u dołu menu docelowego aplikacji. Ta kategoria ma pierwszeństwo przed wszystkimi innymi kategoriami, gdy jest wypełniona w interfejsie użytkownika.

## <a name="cjumplistaddtaskseparator"></a><a name="addtaskseparator"></a> CJumpList::AddTaskSeparator

Dodaje separator między zadaniami.

```
BOOL AddTaskSeparator();
```

### <a name="return-value"></a>Wartość zwracana

Różne od zera, jeśli to się powiedzie, 0, jeśli nie.

## <a name="cjumplistcjumplist"></a><a name="cjumplist"></a> CJumpList::CJumpList

Konstruuje `CJumpList` obiekt.

```
CJumpList(BOOL bAutoCommit = TRUE);
```

### <a name="parameters"></a>Parametry

*bAutoCommit*<br/>
Jeśli ten parametr ma wartość FALSE, lista nie jest automatycznie zatwierdzana w destruktorze.

## <a name="cjumplistclearall"></a><a name="clearall"></a> CJumpList:: ClearAll

Usuwa wszystkie zadania i miejsca docelowe, które zostały dodane do bieżącego wystąpienia `CJumpList` .

```cpp
void ClearAll();
```

### <a name="remarks"></a>Uwagi

Ta metoda czyści i zwalnia wszystkie dane i interfejsy wewnętrzne.

## <a name="cjumplistclearalldestinations"></a><a name="clearalldestinations"></a> CJumpList::ClearAllDestinations

Usuwa wszystkie miejsca docelowe, które zostały dodane do bieżącego wystąpienia CJumpList do tej pory.

```cpp
void ClearAllDestinations();
```

### <a name="remarks"></a>Uwagi

Wywołaj tę funkcję, jeśli musisz usunąć wszystkie miejsca docelowe, które zostały dodane do tej pory w bieżącej sesji tworzenia listy docelowej i ponownie Dodaj inne miejsca docelowe. Jeśli wewnętrzna `ICustomDestinationList` została zainicjowana, pozostaje aktywna.

## <a name="cjumplistcommitlist"></a><a name="commitlist"></a> CJumpList::CommitList

Zamyka transakcję tworzenia listy i zatwierdza zgłoszoną listę do skojarzonego magazynu (w tym przypadku rejestru).

```
BOOL CommitList();
```

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

Zatwierdzenie jest niepodzielne. Jeśli zatwierdzenie zakończy się niepowodzeniem, zostanie zwrócony błąd.  Gdy `CommitList` jest wywoływana, zostanie wyczyszczona bieżąca lista usuniętych elementów. Wywołanie tej metody resetuje obiekt, tak aby nie miał aktywnej transakcji tworzenia listy. Aby zaktualizować listę, należy `BeginList` ponownie wywołać.

## <a name="cjumplistgetdestinationlist"></a><a name="getdestinationlist"></a> CJumpList::GetDestinationList

Pobiera wskaźnik interfejsu do listy docelowej.

```
ICustomDestinationList* GetDestinationList();
```

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

Jeśli lista szybkiego dostępu nie została zainicjowana lub została zatwierdzona lub przerwana, zwrócona wartość będzie RÓWNa NULL.

## <a name="cjumplistgetmaxslots"></a><a name="getmaxslots"></a> CJumpList::GetMaxSlots

Pobiera maksymalną liczbę elementów, włącznie z nagłówkami kategorii, które mogą być wyświetlane w menu docelowym aplikacji wywołującej.

```
UINT GetMaxSlots() const;
```

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

Aplikacje mogą raportować tylko liczbę elementów i nagłówków kategorii połączonych z tą wartością. Jeśli wywołuje do `AppendCategory` , `AppendKnownCategory` lub `AddUserTasks` przekracza tę liczbę, zwróci błąd.

## <a name="cjumplistgetremoveditems"></a><a name="getremoveditems"></a> CJumpList::GetRemovedItems

Zwraca tablicę elementów reprezentujących usunięte miejsca docelowe.

```
IObjectArray* GetRemovedItems();
```

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

Usunięte miejsca docelowe zostaną pobrane podczas inicjowania listy szybkiego dostępu. Podczas generowania nowej listy docelowej aplikacje powinny najpierw przetwarzać listę usuniętych miejsc docelowych, czyszcząc swoje dane śledzenia dla każdego elementu zwróconego przez usunięty moduł wyliczający listę. Jeśli aplikacja próbuje dostarczyć element, który został właśnie usunięty w transakcji, która wywołuje bieżące wywołanie `BeginList` , wywołanie metody, które ponownie dodaliśmy ten element, zakończy się niepowodzeniem, aby upewnić się, że aplikacje są zgodne z usuniętymi listami.

## <a name="cjumplistinitializelist"></a><a name="initializelist"></a> CJumpList::InitializeList

Rozpoczyna transakcję tworzenia listy.

```
BOOL InitializeList();
```

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

Nie musisz jawnie wywoływać tej metody, chyba że chcesz pobrać wskaźnik do `ICustomDestinationList` używania `GetDestinationList` , liczbę dostępnych gniazd przy użyciu `GetMaxSlots` lub listę usuniętych elementów przy użyciu `GetRemovedItems` .

## <a name="cjumplistsetappid"></a><a name="setappid"></a> CJumpList:: setappid

Ustawia identyfikator modelu użytkownika aplikacji dla listy, który zostanie skompilowany.

```cpp
void SetAppID(LPCTSTR strAppID);
```

### <a name="parameters"></a>Parametry

*strAppID*<br/>
Ciąg określający identyfikator modelu użytkownika aplikacji.

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)

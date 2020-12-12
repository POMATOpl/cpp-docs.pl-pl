---
description: 'Dowiedz się więcej na temat: Klasa CRecentFileList'
title: Klasa CRecentFileList
ms.date: 11/04/2016
f1_keywords:
- CRecentFileList
- AFXADV/CRecentFileList
- AFXADV/CRecentFileList::CRecentFileList
- AFXADV/CRecentFileList::Add
- AFXADV/CRecentFileList::GetDisplayName
- AFXADV/CRecentFileList::GetSize
- AFXADV/CRecentFileList::ReadList
- AFXADV/CRecentFileList::Remove
- AFXADV/CRecentFileList::UpdateMenu
- AFXADV/CRecentFileList::WriteList
helpviewer_keywords:
- CRecentFileList [MFC], CRecentFileList
- CRecentFileList [MFC], Add
- CRecentFileList [MFC], GetDisplayName
- CRecentFileList [MFC], GetSize
- CRecentFileList [MFC], ReadList
- CRecentFileList [MFC], Remove
- CRecentFileList [MFC], UpdateMenu
- CRecentFileList [MFC], WriteList
ms.assetid: a77f0524-7584-4582-849a-7e97b76d186e
ms.openlocfilehash: 9433e65336cba1018c7bff8cf3a90e239ae5e3eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301129"
---
# <a name="crecentfilelist-class"></a>Klasa CRecentFileList

Obsługuje kontrolkę ostatnio używanej listy plików (MRU).

## <a name="syntax"></a>Składnia

```
class CRecentFileList
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CRecentFileList::CRecentFileList](#crecentfilelist)|Konstruuje `CRecentFileList` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CRecentFileList:: Add](#add)|Dodaje plik do listy MRU plików.|
|[CRecentFileList:: GetDisplayName](#getdisplayname)|Zawiera nazwę wyświetlaną wyświetlania menu z nazwą pliku MRU.|
|[CRecentFileList:: GetSize](#getsize)|Pobiera liczbę plików z listy ostatnio używanych plików.|
|[CRecentFileList::ReadList](#readlist)|Odczytuje listę plików MRU z rejestru lub. Plik INI.|
|[CRecentFileList:: Remove](#remove)|Usuwa plik z listy ostatnio używanych plików.|
|[CRecentFileList::UpdateMenu](#updatemenu)|Aktualizuje menu wyświetlania listy plików MRU.|
|[CRecentFileList::WriteList](#writelist)|Zapisuje listę plików MRU z rejestru lub. Plik INI.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CRecentFileList:: operator \[\]](#operator_at)|Zwraca `CString` obiekt w danym położeniu.|

## <a name="remarks"></a>Uwagi

Pliki można dodawać do listy MRU plików lub z niej usuwać, a lista plików może być odczytana lub zapisywana w rejestrze lub. Plik INI i menu zawierające listę plików MRU można zaktualizować.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`CRecentFileList`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxadv. h

## <a name="crecentfilelistadd"></a><a name="add"></a> CRecentFileList:: Add

Dodaje plik do listy ostatnio używanych plików (MRU).

```
virtual void Add(LPCTSTR lpszPathName);

virtual void Add(
    LPCTSTR lpszPathName,
    LPCTSTR lpszAppID);

void Add(
    IShellItem* pItem,
    LPCTSTR lpszAppID);

void Add(
    IShellLink* pLink,
    LPCTSTR lpszAppID);

void Add(
    PIDLIST_ABSOLUTE pidl,
    LPCTSTR lpszAppID);
```

### <a name="parameters"></a>Parametry

*lpszPathName*<br/>
Określa nazwę ścieżki, która ma zostać dodana do listy.

*lpszAppID*<br/>
Określa identyfikator modelu użytkownika aplikacji dla aplikacji.

*pItem*<br/>
Określa wskaźnik do elementu powłoki, który ma zostać dodany do listy.

*pLink*<br/>
Określa wskaźnik do linku powłoki, który ma zostać dodany do listy.

*pidl*<br/>
Określa IDLIST dla elementu powłoki, który ma zostać dodany do folderu niedawno używanych dokumentów.

### <a name="remarks"></a>Uwagi

Nazwa pliku zostanie dodana na początku listy MRU. Jeśli nazwa pliku już istnieje na liście MRU, zostanie przeniesiona na początek.

## <a name="crecentfilelistcrecentfilelist"></a><a name="crecentfilelist"></a> CRecentFileList::CRecentFileList

Konstruuje `CRecentFileList` obiekt.

```
CRecentFileList(
    UINT nStart,
    LPCTSTR lpszSection,
    LPCTSTR lpszEntryFormat,
    int nSize,
    int nMaxDispLen = AFX_ABBREV_FILENAME_LEN);
```

### <a name="parameters"></a>Parametry

*Nzaczynać*<br/>
Przesunięcie dla numeracji w menu wyświetlania listy ostatnio używanych plików.

*lpszSection*<br/>
Wskazuje na nazwę sekcji rejestru lub aplikacji. Plik INI, w którym lista plików MRU jest odczytywana i/lub zapisywana.

*lpszEntryFormat*<br/>
Wskazuje ciąg formatu, który ma być używany dla nazw wpisów przechowywanych w rejestrze lub aplikacji. Plik INI.

*nSize*<br/>
Maksymalna liczba plików na liście MRU plików.

*nMaxDispLen*<br/>
Maksymalna długość w znakach, dostępna dla wyświetlania menu nazwy pliku na liście MRU plików.

### <a name="remarks"></a>Uwagi

Ciąg formatu wskazany przez *lpszEntryFormat* powinien zawierać "% d", który będzie używany do podstawiania indeksu każdego elementu MRU. Na przykład, jeśli ciąg formatu jest `"file%d"` wtedy, wpisy będą nazwane `file0` , `file1` i tak dalej.

## <a name="crecentfilelistgetdisplayname"></a><a name="getdisplayname"></a> CRecentFileList:: GetDisplayName

Uzyskuje nazwę wyświetlaną pliku na liście MRU plików do użycia w menu wyświetlania listy MRU.

```
virtual BOOL GetDisplayName(
    CString& strName,
    int nIndex,
    LPCTSTR lpszCurDir,
    int nCurDir,
    BOOL bAtLeastName = TRUE) const;
```

### <a name="parameters"></a>Parametry

*strName*<br/>
Pełna ścieżka pliku, którego nazwa ma zostać wyświetlona na liście menu plików MRU.

*nIndex*<br/>
Indeks pliku (liczony od zera) na liście plików MRU.

*lpszCurDir*<br/>
Ciąg przechowujący bieżący katalog.

*nCurDir*<br/>
Długość bieżącego ciągu katalogu.

*bAtLeastName*<br/>
Jeśli wartość jest różna od zera, wskazuje, że nazwa podstawowa pliku powinna zostać zwrócona, nawet jeśli przekracza maksymalną długość wyświetlaną (przekazana jako parametr *nMaxDispLen* do `CRecentFileList` konstruktora).

### <a name="return-value"></a>Wartość zwracana

**Wartość false** , jeśli na liście ostatnio używanych plików (MRU) nie ma nazwy pliku o określonym indeksie.

### <a name="remarks"></a>Uwagi

Jeśli plik znajduje się w bieżącym katalogu, funkcja pozostawia katalog poza ekranem. Jeśli nazwa pliku jest zbyt długa, katalog i rozszerzenie są usuwane. Jeśli nazwa pliku jest wciąż zbyt długa, nazwa wyświetlana jest ustawiana na pusty ciąg, chyba że *bAtLeastName* jest różna od zera.

## <a name="crecentfilelistgetsize"></a><a name="getsize"></a> CRecentFileList:: GetSize

Pobiera liczbę plików z listy ostatnio używanych plików.

```
int GetSize() const;
```

### <a name="return-value"></a>Wartość zwracana

Liczba plików znajdujących się na liście ostatnio używanych plików (MRU).

## <a name="crecentfilelistoperator--"></a><a name="operator_at"></a> CRecentFileList:: operator []

Przeciążony operator indeksu dolnego ( `[]` ) zwraca pojedynczy `CString` określony przez indeks liczony od zera w *nIndex*.

```
CString& operator[ ](int nindex);
```

### <a name="parameters"></a>Parametry

*nIndex*<br/>
Indeks `CString` w zestawie s liczony od zera `CString` .

## <a name="crecentfilelistreadlist"></a><a name="readlist"></a> CRecentFileList::ReadList

Odczytuje listę ostatnio używanych plików (MRU) z rejestru lub aplikacji. Plik INI.

```
virtual void ReadList();
```

## <a name="crecentfilelistremove"></a><a name="remove"></a> CRecentFileList:: Remove

Usuwa plik z listy ostatnio używanych plików.

```
virtual void Remove(int nIndex);
```

### <a name="parameters"></a>Parametry

*nIndex*<br/>
Indeks pliku, który ma zostać usunięty z listy ostatnio używanych plików (MRU).

## <a name="crecentfilelistupdatemenu"></a><a name="updatemenu"></a> CRecentFileList::UpdateMenu

Aktualizuje menu wyświetlania listy plików MRU.

```
virtual void UpdateMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Parametry

*pCmdUI*<br/>
Wskaźnik do obiektu [CCmdUI](../../mfc/reference/ccmdui-class.md) dla menu Lista ostatnio używanych (MRU) plików.

## <a name="crecentfilelistwritelist"></a><a name="writelist"></a> CRecentFileList::WriteList

Zapisuje listę ostatnio używanych plików (MRU) w rejestrze lub aplikacji. Plik INI.

```
virtual void WriteList();
```

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)

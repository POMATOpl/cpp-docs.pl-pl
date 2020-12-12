---
description: 'Dowiedz się więcej na temat: Klasa CMenu'
title: Klasa CMenu
ms.date: 11/04/2016
f1_keywords:
- CMenu
- AFXWIN/CMenu
- AFXWIN/CMenu::CMenu
- AFXWIN/CMenu::AppendMenu
- AFXWIN/CMenu::Attach
- AFXWIN/CMenu::CheckMenuItem
- AFXWIN/CMenu::CheckMenuRadioItem
- AFXWIN/CMenu::CreateMenu
- AFXWIN/CMenu::CreatePopupMenu
- AFXWIN/CMenu::DeleteMenu
- AFXWIN/CMenu::DeleteTempMap
- AFXWIN/CMenu::DestroyMenu
- AFXWIN/CMenu::Detach
- AFXWIN/CMenu::DrawItem
- AFXWIN/CMenu::EnableMenuItem
- AFXWIN/CMenu::FromHandle
- AFXWIN/CMenu::GetDefaultItem
- AFXWIN/CMenu::GetMenuContextHelpId
- AFXWIN/CMenu::GetMenuInfo
- AFXWIN/CMenu::GetMenuItemCount
- AFXWIN/CMenu::GetMenuItemID
- AFXWIN/CMenu::GetMenuItemInfo
- AFXWIN/CMenu::GetMenuState
- AFXWIN/CMenu::GetMenuString
- AFXWIN/CMenu::GetSafeHmenu
- AFXWIN/CMenu::GetSubMenu
- AFXWIN/CMenu::InsertMenu
- AFXWIN/CMenu::InsertMenuItem
- AFXWIN/CMenu::LoadMenu
- AFXWIN/CMenu::LoadMenuIndirect
- AFXWIN/CMenu::MeasureItem
- AFXWIN/CMenu::ModifyMenu
- AFXWIN/CMenu::RemoveMenu
- AFXWIN/CMenu::SetDefaultItem
- AFXWIN/CMenu::SetMenuContextHelpId
- AFXWIN/CMenu::SetMenuInfo
- AFXWIN/CMenu::SetMenuItemBitmaps
- AFXWIN/CMenu::SetMenuItemInfo
- AFXWIN/CMenu::TrackPopupMenu
- AFXWIN/CMenu::TrackPopupMenuEx
- AFXWIN/CMenu::m_hMenu
helpviewer_keywords:
- CMenu [MFC], CMenu
- CMenu [MFC], AppendMenu
- CMenu [MFC], Attach
- CMenu [MFC], CheckMenuItem
- CMenu [MFC], CheckMenuRadioItem
- CMenu [MFC], CreateMenu
- CMenu [MFC], CreatePopupMenu
- CMenu [MFC], DeleteMenu
- CMenu [MFC], DeleteTempMap
- CMenu [MFC], DestroyMenu
- CMenu [MFC], Detach
- CMenu [MFC], DrawItem
- CMenu [MFC], EnableMenuItem
- CMenu [MFC], FromHandle
- CMenu [MFC], GetDefaultItem
- CMenu [MFC], GetMenuContextHelpId
- CMenu [MFC], GetMenuInfo
- CMenu [MFC], GetMenuItemCount
- CMenu [MFC], GetMenuItemID
- CMenu [MFC], GetMenuItemInfo
- CMenu [MFC], GetMenuState
- CMenu [MFC], GetMenuString
- CMenu [MFC], GetSafeHmenu
- CMenu [MFC], GetSubMenu
- CMenu [MFC], InsertMenu
- CMenu [MFC], InsertMenuItem
- CMenu [MFC], LoadMenu
- CMenu [MFC], LoadMenuIndirect
- CMenu [MFC], MeasureItem
- CMenu [MFC], ModifyMenu
- CMenu [MFC], RemoveMenu
- CMenu [MFC], SetDefaultItem
- CMenu [MFC], SetMenuContextHelpId
- CMenu [MFC], SetMenuInfo
- CMenu [MFC], SetMenuItemBitmaps
- CMenu [MFC], SetMenuItemInfo
- CMenu [MFC], TrackPopupMenu
- CMenu [MFC], TrackPopupMenuEx
- CMenu [MFC], m_hMenu
ms.assetid: 40cacfdc-d45c-4ec7-bf28-991c72812499
ms.openlocfilehash: e1f0caea839e0660db10d055adf2af5fc7deb353
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341584"
---
# <a name="cmenu-class"></a>Klasa CMenu

Hermetyzacja systemu Windows `HMENU` .

## <a name="syntax"></a>Składnia

```
class CMenu : public CObject
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMenu::CMenu](#cmenu)|Konstruuje `CMenu` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMenu::AppendMenu](#appendmenu)|Dołącza nowy element na końcu tego menu.|
|[CMenu:: Attach](#attach)|Dołącza dojście do menu systemu Windows do `CMenu` obiektu.|
|[CMenu::CheckMenuItem](#checkmenuitem)|Umieszcza znacznik wyboru obok lub usuwa znacznik wyboru z elementu menu w menu podręcznym.|
|[CMenu::CheckMenuRadioItem](#checkmenuradioitem)|Umieszcza przycisk radiowy obok elementu menu i usuwa przycisk radiowy ze wszystkich innych elementów menu w grupie.|
|[CMenu:: \ menu](#createmenu)|Tworzy puste menu i dołącza je do `CMenu` obiektu.|
|[CMenu::CreatePopupMenu](#createpopupmenu)|Tworzy puste menu podręczne i dołącza je do `CMenu` obiektu.|
|[CMenu::D eleteMenu](#deletemenu)|Usuwa określony element z menu. Jeśli element menu ma skojarzone menu podręczne, niszczy dojście do menu podręcznego i zwolni używany przez niego pamięć.|
|[CMenu::D eleteTempMap](#deletetempmap)|Usuwa wszystkie `CMenu` obiekty tymczasowe utworzone przez `FromHandle` funkcję członkowską.|
|[CMenu::D estroyMenu](#destroymenu)|Niszczy menu dołączone do `CMenu` obiektu i zwalnia wszystkie pamięci, w których zajmowano menu.|
|[CMenu::D etach](#detach)|Odłącza dojście menu systemu Windows od `CMenu` obiektu i zwraca uchwyt.|
|[CMenu::D rawItem](#drawitem)|Wywoływane przez platformę, gdy wizualny aspekt menu rysowanego przez właściciela zmieni się.|
|[CMenu::EnableMenuItem](#enablemenuitem)|Włącza, wyłącza lub przyciemnia (szare) element menu.|
|[CMenu::FromHandle](#fromhandle)|Zwraca wskaźnik do obiektu, w `CMenu` którym znajduje się uchwyt menu systemu Windows.|
|[CMenu::GetDefaultItem](#getdefaultitem)|Określa domyślny element menu w określonym menu.|
|[CMenu::GetMenuContextHelpId](#getmenucontexthelpid)|Pobiera identyfikator kontekstu pomocy skojarzony z menu.|
|[CMenu::GetMenuInfo](#getmenuinfo)|Pobiera informacje z określonego menu.|
|[CMenu::GetMenuItemCount](#getmenuitemcount)|Określa liczbę elementów w menu podręcznym lub najwyższego poziomu.|
|[CMenu::GetMenuItemID](#getmenuitemid)|Uzyskuje identyfikator elementu menu dla elementu menu znajdującego się w określonej pozycji.|
|[CMenu::GetMenuItemInfo](#getmenuiteminfo)|Pobiera informacje o elemencie menu.|
|[CMenu::GetMenuState](#getmenustate)|Zwraca stan określonego elementu menu lub liczbę elementów w menu podręcznym.|
|[CMenu::GetMenuString](#getmenustring)|Pobiera etykietę określonego elementu menu.|
|[CMenu::GetSafeHmenu](#getsafehmenu)|Zwraca `m_hMenu` opakowany przez ten `CMenu` obiekt.|
|[CMenu::GetSubMenu](#getsubmenu)|Pobiera wskaźnik do menu podręcznego.|
|[CMenu::InsertMenu](#insertmenu)|Wstawia nowy element menu w podanej pozycji, przenosząc pozostałe elementy w dół menu.|
|[CMenu::InsertMenuItem](#insertmenuitem)|Wstawia nowy element menu w podanej pozycji w menu.|
|[CMenu::LoadMenu](#loadmenu)|Ładuje zasób menu z pliku wykonywalnego i dołącza go do `CMenu` obiektu.|
|[CMenu::LoadMenuIndirect](#loadmenuindirect)|Ładuje menu z szablonu menu w pamięci i dołącza je do `CMenu` obiektu.|
|[CMenu::MeasureItem](#measureitem)|Wywoływane przez platformę, aby określić wymiary menu podczas tworzenia menu rysowania przez właściciela.|
|[CMenu::ModifyMenu](#modifymenu)|Zmienia istniejący element menu na określonej pozycji.|
|[CMenu::RemoveMenu](#removemenu)|Usuwa element menu ze skojarzonym menu podręcznym z podanego menu.|
|[CMenu::SetDefaultItem](#setdefaultitem)|Ustawia domyślny element menu dla określonego menu.|
|[CMenu::SetMenuContextHelpId](#setmenucontexthelpid)|Ustawia identyfikator kontekstu pomocy, który ma być skojarzony z menu.|
|[CMenu::SetMenuInfo](#setmenuinfo)|Ustawia informacje w określonym menu.|
|[CMenu::SetMenuItemBitmaps](#setmenuitembitmaps)|Kojarzy określone mapy bitowe znacznika wyboru z elementem menu.|
|[CMenu::SetMenuItemInfo](#setmenuiteminfo)|Zmienia informacje o elemencie menu.|
|[CMenu::TrackPopupMenu](#trackpopupmenu)|Wyświetla ruchome menu wyskakujące w określonej lokalizacji i śledzi wybór elementów z menu podręcznego.|
|[CMenu::TrackPopupMenuEx](#trackpopupmenuex)|Wyświetla ruchome menu wyskakujące w określonej lokalizacji i śledzi wybór elementów z menu podręcznego.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMenu:: operator HMENU](#operator_hmenu)|Pobiera uchwyt obiektu menu.|
|[CMenu:: operator! =](#operator_neq)|Określa, czy dwa obiekty menu nie są równe.|
|[CMenu:: operator = =](#operator_eq_eq)|Określa, czy dwa obiekty menu są równe.|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CMenu:: m_hMenu](#m_hmenu)|Określa uchwyt do menu systemu Windows dołączonego do `CMenu` obiektu.|

## <a name="remarks"></a>Uwagi

Udostępnia funkcje członkowskie do tworzenia, śledzenia, aktualizowania i likwidowania menu.

Utwórz `CMenu` obiekt w ramce stosu jako lokalny, a następnie Wywołaj `CMenu` funkcje członkowskie, aby manipulować nowym menu w razie potrzeby. Następnie Wywołaj [CWnd:: SetMenu](../../mfc/reference/cwnd-class.md#setmenu) , aby ustawić menu w oknie, a następnie bezpośrednio przez wywołanie `CMenu` funkcji [odłączania](#detach) elementu członkowskiego obiektu. `CWnd::SetMenu`Funkcja członkowska ustawia menu okna do nowego menu, powoduje, że okno jest ponownie rysowane, aby odzwierciedlało zmianę menu, a także przekazywać własność menu do okna. Wywołanie `Detach` odłączania HMENU z `CMenu` obiektu, tak że gdy `CMenu` zmienna lokalna kończy się poza zakresem, `CMenu` destruktor obiektu nie podejmuje próby zniszczenia menu, które nie jest już własnością. Samo menu jest automatycznie niszczone, gdy okno zostanie zniszczone.

Za pomocą funkcji składowej [LoadMenuIndirect](#loadmenuindirect) można utworzyć menu na podstawie szablonu w pamięci, ale nie można łatwo utrzymywać menu utworzonego na podstawie zasobu przez wywołanie [LoadMenu](#loadmenu) , a sam zasób menu może być tworzony i modyfikowany przez Edytor menu.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

`CMenu`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxwin. h

## <a name="cmenuappendmenu"></a><a name="appendmenu"></a> CMenu::AppendMenu

Dołącza nowy element na końcu menu.

```
BOOL AppendMenu(
    UINT nFlags,
    UINT_PTR nIDNewItem = 0,
    LPCTSTR lpszNewItem = NULL);

BOOL AppendMenu(
    UINT nFlags,
    UINT_PTR nIDNewItem,
    const CBitmap* pBmp);
```

### <a name="parameters"></a>Parametry

*nFlags*<br/>
Określa informacje o stanie nowego elementu menu po jego dodaniu do menu. Składa się z co najmniej jednej wartości wymienionej w sekcji uwagi.

*nIDNewItem*<br/>
Określa identyfikator polecenia nowego elementu menu lub, jeśli *nFlags* jest ustawiony na MF_POPUP, uchwyt menu ( `HMENU` ) menu podręcznego. Parametr *nIDNewItem* jest ignorowany (niewymagane), jeśli *nFlags* jest ustawiony na MF_SEPARATOR.

*lpszNewItem*<br/>
Określa zawartość nowego elementu menu. Parametr *nFlags* służy do interpretowania *lpszNewItem* w następujący sposób:

|nFlags|Interpretacja lpszNewItem|
|------------|-----------------------------------|
|MF_OWNERDRAW|Zawiera wartość 32-bitowej dostarczonej przez aplikację, która może być używana przez aplikację do obsługi dodatkowych danych skojarzonych z elementem menu. Ta wartość 32-bitowa jest dostępna dla aplikacji podczas przetwarzania WM_MEASUREITEM i WM_DRAWITEM komunikatów. Wartość jest przechowywana w `itemData` składowej struktury dostarczonej z tymi komunikatami.|
|MF_STRING|Zawiera wskaźnik do ciągu zakończonego znakiem null. Jest to domyślna interpretacja.|
|MF_SEPARATOR|Parametr *lpszNewItem* jest ignorowany (niewymagany).|

*pBmp*<br/>
Wskazuje `CBitmap` obiekt, który będzie używany jako element menu.

### <a name="return-value"></a>Wartość zwracana

Różne od zera, jeśli funkcja zakończyła się pomyślnie; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Aplikacja może określić stan elementu menu przez ustawienie wartości w *nFlags*. Gdy *nIDNewItem* określa menu podręczne, będzie częścią menu, do którego jest dołączany. Jeśli to menu zostanie zniszczone, dołączone menu również zostanie zniszczone. Aby uniknąć konfliktu, należy odłączyć menu dołączone od `CMenu` obiektu. Należy zauważyć, że MF_STRING i MF_OWNERDRAW nie są prawidłowe dla wersji mapy bitowej `AppendMenu` .

Poniższa lista zawiera opis flag, które można ustawić w *nFlags*:

- MF_CHECKED działa jako przełącznik z MF_UNCHECKED, aby umieścić znacznik wyboru domyślny obok elementu. Gdy aplikacja dostarcza mapy bitowe znaczników Check (zobacz funkcja członkowska [SetMenuItemBitmaps](#setmenuitembitmaps) ), zostanie wyświetlona mapa bitowa "znacznik wyboru".

- MF_UNCHECKED działa jako przełącznik z MF_CHECKED, aby usunąć znacznik wyboru obok elementu. Gdy aplikacja dostarcza mapy bitowe znaczników Check (zobacz `SetMenuItemBitmaps` funkcja członkowska), wyświetlana jest mapa bitowa "znacznik wyboru".

- MF_DISABLED wyłącza element menu, dzięki czemu nie można go wybrać, ale nie jest przyciemniony.

- MF_ENABLED włącza element menu, aby można go było wybrać i przywrócić go ze stanu wygaszonego.

- MF_GRAYED wyłącza element menu, dzięki czemu nie można go zaznaczyć i przyciemniać.

- MF_MENUBARBREAK umieszcza element w nowym wierszu w menu statycznym lub w nowej kolumnie w menu podręcznym. Nowa kolumna menu podręcznego zostanie oddzielona od starej kolumny przez pionową linię podziału.

- MF_MENUBREAK umieszcza element w nowym wierszu w menu statycznym lub w nowej kolumnie w menu podręcznym. Między kolumnami nie jest umieszczana linia podziału.

- MF_OWNERDRAW określa, że element jest elementem rysowanym przez właściciela. Gdy menu jest wyświetlane po raz pierwszy, okno, do którego należy menu, odbiera komunikat WM_MEASUREITEM, który pobiera wysokość i Szerokość elementu menu. Wiadomość WM_DRAWITEM jest wysyłana za każdym razem, gdy właściciel musi zaktualizować wygląd elementu menu. Ta opcja nie jest prawidłowa dla elementu menu najwyższego poziomu.

- MF_POPUP określa, że element menu jest skojarzony z menu podręcznym. Parametr ID określa uchwyt do menu podręcznego, które ma być skojarzone z elementem. Służy do dodawania menu podręcznego najwyższego poziomu lub hierarchicznego menu podręcznego do elementu menu podręcznego.

- MF_SEPARATOR rysuje wiersz podziału w poziomie. Może być używany tylko w menu podręcznym. Ten wiersz nie może być wyszarzony, wyłączony ani wyróżniony. Inne parametry są ignorowane.

- MF_STRING określa, że element menu jest ciągiem znaków.

Każda z następujących grup zawiera wszystkie flagi, które wzajemnie się wykluczają i nie mogą być używane razem:

- MF_DISABLED, MF_ENABLED i MF_GRAYED

- MF_STRING, MF_OWNERDRAW, MF_SEPARATOR i wersja mapy bitowej

- MF_MENUBARBREAK i MF_MENUBREAK

- MF_CHECKED i MF_UNCHECKED

Gdy zostanie zmienione menu znajdujące się w oknie (bez względu na to, czy okno jest wyświetlane), aplikacja powinna wywołać [CWnd::D rawmenubar](../../mfc/reference/cwnd-class.md#drawmenubar).

### <a name="example"></a>Przykład

  Zobacz przykład dla [CMenu:: \ menu](#createmenu).

## <a name="cmenuattach"></a><a name="attach"></a> CMenu:: Attach

Dołącza istniejące menu systemu Windows do `CMenu` obiektu.

```
BOOL Attach(HMENU hMenu);
```

### <a name="parameters"></a>Parametry

*hMenu*<br/>
Określa uchwyt do menu systemu Windows.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli operacja zakończyła się pomyślnie; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Ta funkcja nie powinna być wywoływana, jeśli menu jest już dołączone do `CMenu` obiektu. Uchwyt menu jest przechowywany w `m_hMenu` elemencie członkowskim danych.

Jeśli menu, które chcesz manipulować, jest już skojarzone z oknem, możesz użyć funkcji [CWnd:: GetMenu](../../mfc/reference/cwnd-class.md#getmenu) , aby uzyskać uchwyt do menu.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCWindowing#21](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]

## <a name="cmenucheckmenuitem"></a><a name="checkmenuitem"></a> CMenu::CheckMenuItem

Dodaje znaczniki wyboru do lub usuwa znaczniki wyboru z elementów menu w menu podręcznym.

```
UINT CheckMenuItem(
    UINT nIDCheckItem,
    UINT nCheck);
```

### <a name="parameters"></a>Parametry

*nIDCheckItem*<br/>
Określa element menu do sprawdzenia, określony przez *nSprawdź*.

*nSprawdź*<br/>
Określa, jak sprawdzić element menu i jak określić położenie elementu w menu. Parametr *nSprawdź* może być kombinacją MF_CHECKED lub MF_UNCHECKED z flagami MF_BYPOSITION lub MF_BYCOMMAND. Flagi te można łączyć za pomocą operatora bitowego or. Mają one następujące znaczenie:

- MF_BYCOMMAND określa, że parametr zwraca identyfikator polecenia istniejącego elementu menu. Jest to opcja domyślna.

- MF_BYPOSITION określa, że parametr podaje pozycję istniejącego elementu menu. Pierwszy element znajduje się na pozycji 0.

- MF_CHECKED działa jako przełącznik z MF_UNCHECKED, aby umieścić znacznik wyboru domyślny obok elementu.

- MF_UNCHECKED działa jako przełącznik z MF_CHECKED, aby usunąć znacznik wyboru obok elementu.

### <a name="return-value"></a>Wartość zwracana

Poprzedni stan elementu: MF_CHECKED lub MF_UNCHECKED lub 0xFFFFFFFF, jeśli element menu nie istnieje.

### <a name="remarks"></a>Uwagi

Parametr *nIDCheckItem* określa element do zmodyfikowania.

Parametr *nIDCheckItem* może identyfikować element menu podręcznego oraz element menu. Nie są wymagane żadne specjalne kroki w celu sprawdzenia elementu menu podręcznego. Elementy menu najwyższego poziomu nie mogą być zaznaczone. Element menu podręcznego musi być sprawdzony według pozycji, ponieważ nie ma skojarzonego z nim identyfikatora elementu menu.

### <a name="example"></a>Przykład

  Zobacz przykład dla [CMenu:: GetMenuState](#getmenustate).

## <a name="cmenucheckmenuradioitem"></a><a name="checkmenuradioitem"></a> CMenu::CheckMenuRadioItem

Sprawdza określony element menu i sprawia, że jest to element radiowy.

```
BOOL CheckMenuRadioItem(
    UINT nIDFirst,
    UINT nIDLast,
    UINT nIDItem,
    UINT nFlags);
```

### <a name="parameters"></a>Parametry

*nIDFirst*<br/>
Określa (jako identyfikator lub przesunięcie, w zależności od wartości *nFlags*) pierwszy element menu w grupie przycisków radiowych.

*nIDLast*<br/>
Określa (jako identyfikator lub przesunięcie, w zależności od wartości *nFlags*) ostatni element menu w grupie przycisków radiowych.

*nIDItem*<br/>
Określa (jako identyfikator lub przesunięcie, w zależności od wartości *nFlags*) element w grupie, który zostanie sprawdzony przy użyciu przycisku radiowego.

*nFlags*<br/>
Określa interpretację elementów *nIDFirst*, *nIDLast* i *nIDItem* w następujący sposób:

|nFlags|Interpretacja|
|------------|--------------------|
|MF_BYCOMMAND|Określa, że parametr zwraca identyfikator polecenia istniejącego elementu menu. Jest to wartość domyślna, jeśli nie MF_BYCOMMAND ani MF_BYPOSITION.|
|MF_BYPOSITION|Określa, że parametr podaje pozycję istniejącego elementu menu. Pierwszy element znajduje się na pozycji 0.|

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie 0

### <a name="remarks"></a>Uwagi

W tym samym czasie funkcja usuwa wszystkie inne elementy menu w skojarzonej grupie i czyści flagę typu elementu radiowego dla tych elementów. Zaznaczony element jest wyświetlany przy użyciu przycisku radiowego (lub punktora) zamiast mapy bitowej znacznika wyboru.

### <a name="example"></a>Przykład

  Zapoznaj się z przykładem [ON_COMMAND_RANGE](message-map-macros-mfc.md#on_command_range).

## <a name="cmenucmenu"></a><a name="cmenu"></a> CMenu::CMenu

Tworzy puste menu i dołącza je do `CMenu` obiektu.

```
CMenu();
```

### <a name="remarks"></a>Uwagi

Menu nie jest tworzone, dopóki nie zostanie wywołana jedna z funkcji tworzenia lub ładowania elementu członkowskiego `CMenu:`

- [Menu](#createmenu)

- [CreatePopupMenu](#createpopupmenu)

- [LoadMenu](#loadmenu)

- [LoadMenuIndirect](#loadmenuindirect)

- [Dołącz](#attach)

## <a name="cmenucreatemenu"></a><a name="createmenu"></a> CMenu:: \ menu

Tworzy menu i dołącza je do `CMenu` obiektu.

```
BOOL CreateMenu();
```

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli menu zostało utworzone pomyślnie; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Menu jest początkowo puste. Elementy menu można dodawać przy użyciu `AppendMenu` `InsertMenu` funkcji lub.

Jeśli menu jest przypisane do okna, zostanie automatycznie zniszczone, gdy okno zostanie zniszczone.

Przed wyjściem aplikacja musi zwolnić zasoby systemowe skojarzone z menu, jeśli menu nie jest przypisane do okna. Aplikacja zwolni menu, wywołując funkcję elementu członkowskiego [DestroyMenu](#destroymenu) .

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCWindowing#22](../../mfc/reference/codesnippet/cpp/cmenu-class_2.cpp)]

## <a name="cmenucreatepopupmenu"></a><a name="createpopupmenu"></a> CMenu::CreatePopupMenu

Tworzy menu podręczne i dołącza je do `CMenu` obiektu.

```
BOOL CreatePopupMenu();
```

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli menu podręczne zostało pomyślnie utworzone; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Menu jest początkowo puste. Elementy menu można dodawać przy użyciu `AppendMenu` `InsertMenu` funkcji lub. Aplikacja może dodać menu podręczne do istniejącego menu lub menu podręcznego. `TrackPopupMenu`Funkcja członkowska może służyć do wyświetlania tego menu jako swobodnego menu podręcznego oraz do śledzenia wybranych opcji w menu podręcznym.

Jeśli menu jest przypisane do okna, zostanie automatycznie zniszczone, gdy okno zostanie zniszczone. Jeśli menu jest dodawane do istniejącego menu, zostanie automatycznie zniszczone po zniszczeniu tego menu.

Przed wyjściem aplikacja musi zwolnić zasoby systemowe skojarzone z menu podręcznym, jeśli menu nie jest przypisane do okna. Aplikacja zwolni menu, wywołując funkcję elementu członkowskiego [DestroyMenu](#destroymenu) .

### <a name="example"></a>Przykład

  Zobacz przykład dla [CMenu:: \ menu](#createmenu).

## <a name="cmenudeletemenu"></a><a name="deletemenu"></a> CMenu::D eleteMenu

Usuwa element z menu.

```
BOOL DeleteMenu(
    UINT nPosition,
    UINT nFlags);
```

### <a name="parameters"></a>Parametry

*Npozycji*<br/>
Określa element menu, który ma zostać usunięty, określony przez *nFlags*.

*nFlags*<br/>
Służy do interpretowania *npozycji* w następujący sposób:

|nFlags|Interpretacja Npozycji|
|------------|---------------------------------|
|MF_BYCOMMAND|Określa, że parametr zwraca identyfikator polecenia istniejącego elementu menu. Jest to wartość domyślna, jeśli nie MF_BYCOMMAND ani MF_BYPOSITION.|
|MF_BYPOSITION|Określa, że parametr podaje pozycję istniejącego elementu menu. Pierwszy element znajduje się na pozycji 0.|

### <a name="return-value"></a>Wartość zwracana

Różne od zera, jeśli funkcja zakończyła się pomyślnie; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Jeśli element menu ma skojarzone menu podręczne, `DeleteMenu` niszczy dojście do menu podręcznego i zwolni pamięć używaną przez menu podręczne.

Gdy zostanie zmienione menu znajdujące się w oknie (bez względu na to, czy okno jest wyświetlane), aplikacja musi wywołać [CWnd::D rawmenubar](../../mfc/reference/cwnd-class.md#drawmenubar).

### <a name="example"></a>Przykład

  Zobacz przykład dla [CWnd:: GetMenu](../../mfc/reference/cwnd-class.md#getmenu).

## <a name="cmenudeletetempmap"></a><a name="deletetempmap"></a> CMenu::D eleteTempMap

Wywoływana automatycznie przez `CWinApp` program obsługi czasu bezczynności, usuwa wszystkie `CMenu` obiekty tymczasowe utworzone przez funkcję członkowską [FromHandle](#fromhandle) .

```
static void PASCAL DeleteTempMap();
```

### <a name="remarks"></a>Uwagi

`DeleteTempMap` odłącza obiekt menu systemu Windows dołączony do obiektu tymczasowego `CMenu` przed usunięciem `CMenu` obiektu.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCWindowing#23](../../mfc/reference/codesnippet/cpp/cmenu-class_3.cpp)]

## <a name="cmenudestroymenu"></a><a name="destroymenu"></a> CMenu::D estroyMenu

Niszczy menu i wszystkie użyte zasoby systemu Windows.

```
BOOL DestroyMenu();
```

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli menu jest zniszczone; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Menu jest odłączone od `CMenu` obiektu przed jego zniszczeniem. Funkcja systemu Windows `DestroyMenu` jest wywoływana automatycznie w `CMenu` destruktorze.

### <a name="example"></a>Przykład

  Zobacz przykład dla [CMenu:: \ menu](#createmenu).

## <a name="cmenudetach"></a><a name="detach"></a> CMenu::D etach

Odłącza menu systemu Windows od `CMenu` obiektu i zwraca dojście.

```
HMENU Detach();
```

### <a name="return-value"></a>Wartość zwracana

Jeśli to się powiedzie, dojście typu HMENU do menu systemu Windows. w przeciwnym razie wartość NULL.

### <a name="remarks"></a>Uwagi

`m_hMenu`Element członkowski danych ma wartość null.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCWindowing#21](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]

## <a name="cmenudrawitem"></a><a name="drawitem"></a> CMenu::D rawItem

Wywoływane przez platformę, gdy wizualny aspekt menu rysowanego przez właściciela zmieni się.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parametry

*lpDrawItemStruct*<br/>
Wskaźnik do struktury [DRAWITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-drawitemstruct) , który zawiera informacje o wymaganym typie rysunku.

### <a name="remarks"></a>Uwagi

`itemAction`Element członkowski `DRAWITEMSTRUCT` struktury definiuje akcję rysowania, która ma zostać wykonana. Przesłoń tę funkcję elementu członkowskiego, aby zaimplementować rysowanie dla obiektu rysowania przez właściciela `CMenu` . Aplikacja powinna przywrócić wszystkie obiekty interfejsu GDI (Graphics Device Interface) wybrane dla kontekstu wyświetlania dostarczonego w *lpDrawItemStruct* przed zakończeniem tej funkcji elementu członkowskiego.

Opis struktury można znaleźć w temacie [CWnd:: OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) `DRAWITEMSTRUCT` .

### <a name="example"></a>Przykład

Następujący kod pochodzi z przykładu MFC [CTRLTEST](../../overview/visual-cpp-samples.md) :

[!code-cpp[NVC_MFCWindowing#24](../../mfc/reference/codesnippet/cpp/cmenu-class_4.cpp)]

## <a name="cmenuenablemenuitem"></a><a name="enablemenuitem"></a> CMenu::EnableMenuItem

Włącza, wyłącza lub przyciemnia element menu.

```
UINT EnableMenuItem(
    UINT nIDEnableItem,
    UINT nEnable);
```

### <a name="parameters"></a>Parametry

*nIDEnableItem*<br/>
Określa element menu, który ma być włączony, określony przez *nEnable*. Ten parametr może określać elementy menu podręcznego oraz standardowe elementy menu.

*nEnable*<br/>
Określa akcję do wykonania. Może to być kombinacja MF_DISABLED, MF_ENABLED lub MF_GRAYED z MF_BYCOMMAND lub MF_BYPOSITION. Te wartości można łączyć za pomocą operatora bitowego or. Te wartości mają następujące znaczenie:

- MF_BYCOMMAND określa, że parametr zwraca identyfikator polecenia istniejącego elementu menu. Jest to opcja domyślna.

- MF_BYPOSITION określa, że parametr podaje pozycję istniejącego elementu menu. Pierwszy element znajduje się na pozycji 0.

- MF_DISABLED wyłącza element menu, dzięki czemu nie można go wybrać, ale nie jest przyciemniony.

- MF_ENABLED włącza element menu, aby można go było wybrać i przywrócić go ze stanu wygaszonego.

- MF_GRAYED wyłącza element menu, dzięki czemu nie można go zaznaczyć i przyciemniać.

### <a name="return-value"></a>Wartość zwracana

Poprzedni stan (MF_DISABLED, MF_ENABLED lub MF_GRAYED) lub-1, jeśli jest nieprawidłowy.

### <a name="remarks"></a>Uwagi

Funkcje [](#createmenu)elementu członkowskiego " [InsertMenu](#insertmenu), [ModifyMenu](#modifymenu)i [LoadMenuIndirect](#loadmenuindirect) " mogą również ustawiać stan (włączony, wyłączony lub wyszarzony) elementu menu.

Użycie wartości MF_BYPOSITION wymaga zastosowania odpowiedniej aplikacji `CMenu` . Jeśli zostanie `CMenu` użyty pasek menu, ma to na przykład element menu najwyższego poziomu (element na pasku menu). Aby ustawić stan elementu w podręcznym lub zagnieżdżonym menu podręcznym według położenia, aplikacja musi określić `CMenu` menu podręczne.

Gdy aplikacja określa flagę MF_BYCOMMAND, system Windows sprawdza wszystkie elementy menu podręcznego, które są podrzędne względem `CMenu` . w związku z tym, jeśli nie istnieją zduplikowane elementy menu, użycie `CMenu` paska menu jest wystarczające.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCWindowing#25](../../mfc/reference/codesnippet/cpp/cmenu-class_5.cpp)]

## <a name="cmenufromhandle"></a><a name="fromhandle"></a> CMenu::FromHandle

Zwraca wskaźnik do `CMenu` obiektu przydanego uchwytu systemu Windows do menu.

```
static CMenu* PASCAL FromHandle(HMENU hMenu);
```

### <a name="parameters"></a>Parametry

*hMenu*<br/>
Uchwyt systemu Windows do menu.

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do elementu `CMenu` , który może być tymczasowy lub trwały.

### <a name="remarks"></a>Uwagi

Jeśli `CMenu` obiekt nie jest jeszcze dołączony do obiektu menu systemu Windows, `CMenu` zostanie utworzony i dołączony obiekt tymczasowy.

Ten `CMenu` obiekt tymczasowy jest prawidłowy tylko do następnego czasu bezczynności aplikacji w pętli zdarzeń, w którym wszystkie obiekty tymczasowe są usuwane.

### <a name="example"></a>Przykład

  Zobacz przykład dla [CMenu:: \ menu](#createmenu).

## <a name="cmenugetdefaultitem"></a><a name="getdefaultitem"></a> CMenu::GetDefaultItem

Określa domyślny element menu w określonym menu.

```
UINT GetDefaultItem(
    UINT gmdiFlags,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>Parametry

*gmdiFlags*<br/>
Wartość określająca, w jaki sposób funkcja wyszukuje elementy menu. Ten parametr może mieć wartość None, one lub kombinację następujących wartości:

|Wartość|Znaczenie|
|-----------|-------------|
|GMDI_GOINTOPOPUPS|Określa, że jeśli domyślnym elementem jest ten, który otwiera podmenu, funkcja ma przeszukiwać w odpowiadającym podmenu rekursywnie. Jeśli podmenu nie ma elementu domyślnego, wartość zwracana identyfikuje element, który otwiera podmenu.<br /><br /> Domyślnie funkcja zwraca pierwszy element domyślny w określonym menu, niezależnie od tego, czy jest to element, który otwiera podmenu.|
|GMDI_USEDISABLED|Określa, że funkcja ma zwracać element domyślny, nawet jeśli jest wyłączony.<br /><br /> Domyślnie funkcja pomija elementy wyłączone lub wyszarzone.|

*fByPos*<br/>
Wartość określająca, czy ma zostać pobrany identyfikator elementu menu, czy jego pozycja. Jeśli ten parametr ma wartość FALSE, zwracany jest identyfikator. W przeciwnym razie pozycja jest zwracana.

### <a name="return-value"></a>Wartość zwracana

Jeśli funkcja się powiedzie, wartość zwracana jest identyfikatorem lub pozycją elementu menu. Jeśli funkcja się nie powiedzie, zwracana wartość to-1.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje zachowanie funkcji Win32 [GetMenuDefaultItem](/windows/win32/api/winuser/nf-winuser-getmenudefaultitem), zgodnie z opisem w Windows SDK.

### <a name="example"></a>Przykład

  Zobacz przykład dla [CMenu:: InsertMenu](#insertmenu).

## <a name="cmenugetmenucontexthelpid"></a><a name="getmenucontexthelpid"></a> CMenu::GetMenuContextHelpId

Pobiera identyfikator pomocy kontekstowej skojarzony z `CMenu` .

```
DWORD GetMenuContextHelpId() const;
```

### <a name="return-value"></a>Wartość zwracana

Identyfikator pomocy kontekstowej, który jest aktualnie skojarzony z, `CMenu` Jeśli ma jeden; zero w przeciwnym razie.

### <a name="example"></a>Przykład

  Zobacz przykład dla [CMenu:: InsertMenu](#insertmenu).

## <a name="cmenugetmenuinfo"></a><a name="getmenuinfo"></a> CMenu::GetMenuInfo

Pobiera informacje z menu.

```
BOOL GetMenuInfo(LPMENUINFO lpcmi) const;
```

### <a name="parameters"></a>Parametry

*lpcmi*<br/>
Wskaźnik do struktury [MENUINFO](/windows/win32/api/winuser/ns-winuser-menuinfo) zawierającej informacje dla menu.

### <a name="return-value"></a>Wartość zwracana

Jeśli funkcja się powiedzie, wartość zwracana jest różna od zera. w przeciwnym razie wartość zwracana jest równa zero.

### <a name="remarks"></a>Uwagi

Wywołaj tę funkcję, aby pobrać informacje o menu.

## <a name="cmenugetmenuitemcount"></a><a name="getmenuitemcount"></a> CMenu::GetMenuItemCount

Określa liczbę elementów w menu podręcznym lub najwyższego poziomu.

```
UINT GetMenuItemCount() const;
```

### <a name="return-value"></a>Wartość zwracana

Liczba elementów w menu, jeśli funkcja się powiedzie; w przeciwnym razie-1.

### <a name="example"></a>Przykład

  Zobacz przykład dla [CWnd:: GetMenu](../../mfc/reference/cwnd-class.md#getmenu).

## <a name="cmenugetmenuitemid"></a><a name="getmenuitemid"></a> CMenu::GetMenuItemID

Uzyskuje identyfikator elementu menu dla elementu menu znajdującego się w pozycji zdefiniowanej przez *nPos*.

```
UINT GetMenuItemID(int nPos) const;
```

### <a name="parameters"></a>Parametry

*nPos*<br/>
Określa pozycję (liczony od zera) elementu menu, którego identyfikator jest pobierany.

### <a name="return-value"></a>Wartość zwracana

Identyfikator elementu dla określonego elementu w menu podręcznym, jeśli funkcja się powiedzie. Jeśli określony element jest menu podręcznym (w przeciwieństwie do elementu w menu podręcznym), zwracana wartość to-1. Jeśli *nPos* odnosi się do elementu menu separator, wartość zwracana wynosi 0.

### <a name="example"></a>Przykład

  Zobacz przykład dla [CMenu:: InsertMenu](#insertmenu).

## <a name="cmenugetmenuiteminfo"></a><a name="getmenuiteminfo"></a> CMenu::GetMenuItemInfo

Pobiera informacje o elemencie menu.

```
BOOL GetMenuItemInfo(
    UINT uItem,
    LPMENUITEMINFO lpMenuItemInfo,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>Parametry

*uItem*<br/>
Identyfikator lub pozycja elementu menu, w którym mają zostać wyświetlone informacje. Znaczenie tego parametru zależy od wartości `ByPos` .

*lpMenuItemInfo*<br/>
Wskaźnik do [kojarząca](/windows/win32/api/winuser/ns-winuser-menuiteminfow), zgodnie z opisem w Windows SDK, który zawiera informacje o menu.

*fByPos*<br/>
Wartość określająca znaczenie `nIDItem` . Domyślnie `ByPos` ma wartość false, co oznacza, że uItem jest identyfikatorem elementu menu. Jeśli `ByPos` nie jest ustawiona na wartość false, wskazuje położenie elementu menu.

### <a name="return-value"></a>Wartość zwracana

Jeśli funkcja się powiedzie, wartość zwracana jest różna od zera. Jeśli funkcja się nie powiedzie, zwracana wartość jest równa zero. Aby uzyskać rozszerzone informacje o błędach, należy użyć funkcji [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)systemu Win32, zgodnie z opisem w Windows SDK.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje zachowanie funkcji Win32 [GetMenuItemInfo](/windows/win32/api/winuser/nf-winuser-getmenuiteminfow), zgodnie z opisem w Windows SDK. Należy pamiętać, że w implementacji MFC `GetMenuItemInfo` , nie należy używać dojścia do menu.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCWindowing#26](../../mfc/reference/codesnippet/cpp/cmenu-class_6.cpp)]

## <a name="cmenugetmenustate"></a><a name="getmenustate"></a> CMenu::GetMenuState

Zwraca stan określonego elementu menu lub liczbę elementów w menu podręcznym.

```
UINT GetMenuState(
    UINT nID,
    UINT nFlags) const;
```

### <a name="parameters"></a>Parametry

*nID*<br/>
Określa identyfikator elementu menu, określony przez *nFlags*.

*nFlags*<br/>
Określa charakter *NID*. Może to być jedna z następujących wartości:

- MF_BYCOMMAND określa, że parametr zwraca identyfikator polecenia istniejącego elementu menu. Jest to opcja domyślna.

- MF_BYPOSITION określa, że parametr podaje pozycję istniejącego elementu menu. Pierwszy element znajduje się na pozycji 0.

### <a name="return-value"></a>Wartość zwracana

Wartość 0xFFFFFFFF, jeśli określony element nie istnieje. Jeśli *NID* identyfikuje menu podręczne, bajt o wysokim zamówieniu zawiera liczbę elementów w menu podręcznym, a niska wartość bajtu zawiera flagi menu skojarzone z menu podręcznym. W przeciwnym razie wartość zwracana jest maską (Boolean lub) wartości z poniższej listy (ta maska opisuje stan elementu menu, który identyfikuje *NID* ):

- MF_CHECKED działa jako przełącznik z MF_UNCHECKED, aby umieścić znacznik wyboru domyślny obok elementu. Gdy aplikacja dostarcza mapy bitowe znaczników Check (zobacz `SetMenuItemBitmaps` funkcja członkowska), wyświetlana jest mapa bitowa "znacznik wyboru".

- MF_DISABLED wyłącza element menu, dzięki czemu nie można go wybrać, ale nie jest przyciemniony.

- MF_ENABLED włącza element menu, aby można go było wybrać i przywrócić go ze stanu wygaszonego. Należy zauważyć, że wartość tej stałej jest równa 0; Aplikacja nie powinna testować względem 0 w przypadku niepowodzenia podczas korzystania z tej wartości.

- MF_GRAYED wyłącza element menu, dzięki czemu nie można go zaznaczyć i przyciemniać.

- MF_MENUBARBREAK umieszcza element w nowym wierszu w menu statycznym lub w nowej kolumnie w menu podręcznym. Nowa kolumna menu podręcznego zostanie oddzielona od starej kolumny przez pionową linię podziału.

- MF_MENUBREAK umieszcza element w nowym wierszu w menu statycznym lub w nowej kolumnie w menu podręcznym. Między kolumnami nie jest umieszczana linia podziału.

- MF_SEPARATOR rysuje wiersz podziału w poziomie. Może być używany tylko w menu podręcznym. Ten wiersz nie może być wyszarzony, wyłączony ani wyróżniony. Inne parametry są ignorowane.

- MF_UNCHECKED działa jako przełącznik z MF_CHECKED, aby usunąć znacznik wyboru obok elementu. Gdy aplikacja dostarcza mapy bitowe znaczników Check (zobacz `SetMenuItemBitmaps` funkcja członkowska), wyświetlana jest mapa bitowa "znacznik wyboru". Należy zauważyć, że wartość tej stałej jest równa 0; Aplikacja nie powinna testować względem 0 w przypadku niepowodzenia podczas korzystania z tej wartości.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCWindowing#27](../../mfc/reference/codesnippet/cpp/cmenu-class_7.cpp)]

## <a name="cmenugetmenustring"></a><a name="getmenustring"></a> CMenu::GetMenuString

Kopiuje etykietę określonego elementu menu do określonego buforu.

```
int GetMenuString(
    UINT nIDItem,
    LPTSTR lpString,
    int nMaxCount,
    UINT nFlags) const;

int GetMenuString(
    UINT nIDItem,
    CString& rString,
    UINT nFlags) const;
```

### <a name="parameters"></a>Parametry

*nIDItem*<br/>
Określa identyfikator liczby całkowitej elementu menu lub przesunięcie elementu menu w menu, w zależności od wartości *nFlags*.

*lpString*<br/>
Wskazuje bufor, który ma otrzymać etykietę.

*rString*<br/>
Odwołanie do `CString` obiektu, który ma otrzymać skopiowany ciąg menu.

*nMaxCount*<br/>
Określa maksymalną długość etykiety (w znakach), która ma zostać skopiowana. Jeśli etykieta jest dłuższa niż wartość maksymalna określona w *nMaxCount*, dodatkowe znaki są obcinane.

*nFlags*<br/>
Określa interpretację parametru *nIDItem* . Może to być jedna z następujących wartości:

|nFlags|Interpretacja nIDItem|
|------------|-------------------------------|
|MF_BYCOMMAND|Określa, że parametr zwraca identyfikator polecenia istniejącego elementu menu. Jest to wartość domyślna, jeśli nie MF_BYCOMMAND ani MF_BYPOSITION.|
|MF_BYPOSITION|Określa, że parametr podaje pozycję istniejącego elementu menu. Pierwszy element znajduje się na pozycji 0.|

### <a name="return-value"></a>Wartość zwracana

Określa rzeczywistą liczbę znaków skopiowaną do bufora bez uwzględnienia terminatora wartości null.

### <a name="remarks"></a>Uwagi

Wartość parametru *nMaxCount* powinna być większa niż liczba znaków w etykiecie, aby pomieścić znak null, który kończy ciąg.

### <a name="example"></a>Przykład

  Zobacz przykład dla [CMenu:: InsertMenu](#insertmenu).

## <a name="cmenugetsafehmenu"></a><a name="getsafehmenu"></a> CMenu::GetSafeHmenu

Zwraca HMENU opakowany przez ten `CMenu` obiekt lub wskaźnik o wartości null `CMenu` .

```
HMENU GetSafeHmenu() const;
```

### <a name="example"></a>Przykład

  Zobacz przykład dla [CMenu:: LoadMenu](#loadmenu).

## <a name="cmenugetsubmenu"></a><a name="getsubmenu"></a> CMenu::GetSubMenu

Pobiera `CMenu` obiekt menu wyskakującego.

```
CMenu* GetSubMenu(int nPos) const;
```

### <a name="parameters"></a>Parametry

*nPos*<br/>
Określa pozycję menu rozwijanego zawartego w menu. Wartości pozycji zaczynają się od 0 dla pierwszego elementu menu. W tej funkcji nie można używać identyfikatora menu podręcznego.

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do obiektu, `CMenu` którego `m_hMenu` członek zawiera uchwyt do menu podręcznego, jeśli w podanym miejscu istnieje menu podręczne; w przeciwnym razie wartość null. Jeśli `CMenu` obiekt nie istnieje, zostanie utworzony tymczasowy. `CMenu`Zwrócony wskaźnik nie powinien być przechowywany.

### <a name="example"></a>Przykład

  Zobacz przykład dla [CMenu:: TrackPopupMenu](#trackpopupmenu).

## <a name="cmenuinsertmenu"></a><a name="insertmenu"></a> CMenu::InsertMenu

Wstawia nowy element menu na pozycji określonej przez *npozycji* i przenosi inne elementy w dół menu.

```
BOOL InsertMenu(
    UINT nPosition,
    UINT nFlags,
    UINT_PTR nIDNewItem = 0,
    LPCTSTR lpszNewItem = NULL);

BOOL InsertMenu(
    UINT nPosition,
    UINT nFlags,
    UINT_PTR nIDNewItem,
    const CBitmap* pBmp);
```

### <a name="parameters"></a>Parametry

*Npozycji*<br/>
Określa element menu, przed którym ma zostać wstawiony nowy element menu. Parametr *nFlags* może służyć do interpretowania *npozycji* w następujący sposób:

|nFlags|Interpretacja Npozycji|
|------------|---------------------------------|
|MF_BYCOMMAND|Określa, że parametr zwraca identyfikator polecenia istniejącego elementu menu. Jest to wartość domyślna, jeśli nie MF_BYCOMMAND ani MF_BYPOSITION.|
|MF_BYPOSITION|Określa, że parametr podaje pozycję istniejącego elementu menu. Pierwszy element znajduje się na pozycji 0. Jeśli *npozycji* ma wartość-1, nowy element menu jest dołączany na końcu menu.|

*nFlags*<br/>
Określa, jak *npozycji* jest interpretowany i określa informacje o stanie nowego elementu menu po dodaniu go do menu. Aby uzyskać listę flag, które mogą być ustawione, zobacz funkcja członkowska [AppendMenu](#appendmenu) . Aby określić więcej niż jedną wartość, użyj operatora bitowego or, aby połączyć je z flagą MF_BYCOMMAND lub MF_BYPOSITION.

*nIDNewItem*<br/>
Określa identyfikator polecenia nowego elementu menu lub, jeśli *nFlags* jest ustawiona na MF_POPUP, uchwyt menu (HMENU) menu podręcznego. Parametr *nIDNewItem* jest ignorowany (niewymagane), jeśli *nFlags* jest ustawiony na MF_SEPARATOR.

*lpszNewItem*<br/>
Określa zawartość nowego elementu menu. *nFlags* może służyć do interpretowania *lpszNewItem* w następujący sposób:

|nFlags|Interpretacja lpszNewItem|
|------------|-----------------------------------|
|MF_OWNERDRAW|Zawiera wartość 32-bitowej dostarczonej przez aplikację, która może być używana przez aplikację do obsługi dodatkowych danych skojarzonych z elementem menu. Ta wartość 32-bitowa jest dostępna dla aplikacji w `itemData` składowej struktury dostarczonej przez [WM_MEASUREITEM](/windows/win32/Controls/wm-measureitem) i [WM_DRAWITEM](/windows/win32/Controls/wm-drawitem) komunikatów. Te komunikaty są wysyłane, gdy element menu jest początkowo wyświetlany lub zmieniany.|
|MF_STRING|Zawiera długi wskaźnik do ciągu zakończonego wartością null. Jest to domyślna interpretacja.|
|MF_SEPARATOR|Parametr *lpszNewItem* jest ignorowany (niewymagany).|

*pBmp*<br/>
Wskazuje `CBitmap` obiekt, który będzie używany jako element menu.

### <a name="return-value"></a>Wartość zwracana

Różne od zera, jeśli funkcja zakończyła się pomyślnie; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Aplikacja może określić stan elementu menu przez ustawienie wartości w *nFlags*.

Gdy zostanie zmienione menu znajdujące się w oknie (niezależnie od tego, czy okno jest wyświetlane), aplikacja powinna wywołać `CWnd::DrawMenuBar` .

Gdy *nIDNewItem* określa menu wyskakującego, będzie częścią menu, w którym jest wstawiany. Jeśli to menu zostanie zniszczone, wstawione menu również zostanie zniszczone. Wstawione menu powinno być odłączone od obiektu, `CMenu` Aby uniknąć konfliktu.

Jeśli okno podrzędne interfejsu aktywnego wielu dokumentów (MDI) jest zmaksymalizowane, a aplikacja wstawi menu podręczne do menu aplikacji MDI przez wywołanie tej funkcji i określenie flagi MF_BYPOSITION, menu zostanie wstawione o jedną pozycję dalej niż oczekiwano. Dzieje się tak, ponieważ menu sterowania aktywnego okna podrzędnego MDI zostanie wstawione do pierwszej pozycji paska menu okna ramki MDI. Aby odpowiednio ustawić menu, aplikacja musi dodać 1 do wartości pozycji, która będzie używana w przeciwnym razie. Aplikacja może użyć komunikatu WM_MDIGETACTIVE, aby określić, czy aktywne okno podrzędne jest zmaksymalizowane.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCWindowing#28](../../mfc/reference/codesnippet/cpp/cmenu-class_8.cpp)]

## <a name="cmenuinsertmenuitem"></a><a name="insertmenuitem"></a> CMenu::InsertMenuItem

Wstawia nowy element menu w podanej pozycji w menu.

```
BOOL InsertMenuItem(
    UINT uItem,
    LPMENUITEMINFO lpMenuItemInfo,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>Parametry

*uItem*<br/>
Zobacz opis elementu *uItem* w [InsertMenuItem](/windows/win32/api/winuser/nf-winuser-insertmenuitemw) w Windows SDK.

*lpMenuItemInfo*<br/>
Zobacz opis elementu *lpmii* w `InsertMenuItem` Windows SDK.

*fByPos*<br/>
Zobacz opis elementu *fByPosition* w `InsertMenuItem` Windows SDK.

### <a name="remarks"></a>Uwagi

Ta funkcja otacza [InsertMenuItem](/windows/win32/api/winuser/nf-winuser-insertmenuitemw), opisane w Windows SDK.

## <a name="cmenuloadmenu"></a><a name="loadmenu"></a> CMenu::LoadMenu

Ładuje zasób menu z pliku wykonywalnego aplikacji i dołącza go do `CMenu` obiektu.

```
BOOL LoadMenu(LPCTSTR lpszResourceName);
BOOL LoadMenu(UINT nIDResource);
```

### <a name="parameters"></a>Parametry

*lpszResourceName*<br/>
Wskazuje ciąg zakończony znakiem null, który zawiera nazwę zasobu menu do załadowania.

*nIDResource*<br/>
Określa identyfikator menu zasobu menu do załadowania.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli zasób menu został pomyślnie załadowany; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Przed wyjściem aplikacja musi zwolnić zasoby systemowe skojarzone z menu, jeśli menu nie jest przypisane do okna. Aplikacja zwolni menu, wywołując funkcję elementu członkowskiego [DestroyMenu](#destroymenu) .

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCWindowing#29](../../mfc/reference/codesnippet/cpp/cmenu-class_9.cpp)]

## <a name="cmenuloadmenuindirect"></a><a name="loadmenuindirect"></a> CMenu::LoadMenuIndirect

Ładuje zasób z szablonu menu w pamięci i dołącza go do `CMenu` obiektu.

```
BOOL LoadMenuIndirect(const void* lpMenuTemplate);
```

### <a name="parameters"></a>Parametry

*lpMenuTemplate*<br/>
Wskazuje szablon menu (który jest pojedynczą strukturą [MENUITEMTEMPLATEHEADER](/windows/win32/api/winuser/ns-winuser-menuitemtemplateheader) i kolekcją co najmniej jednej struktury [MENUITEMTEMPLATE](/windows/win32/api/winuser/ns-winuser-menuitemtemplate) ). Aby uzyskać więcej informacji na temat tych dwóch struktur, zobacz Windows SDK.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli zasób menu został pomyślnie załadowany; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Szablon menu jest nagłówkiem, po którym następuje kolekcja co najmniej jednej struktury [MENUITEMTEMPLATE](/windows/win32/api/winuser/ns-winuser-menuitemtemplate) , z których każdy może zawierać jeden lub więcej elementów menu i menu podręcznych.

Numer wersji powinien mieć wartość 0.

`mtOption`Flagi powinny zawierać MF_END dla ostatniego elementu z listy podręcznej i dla ostatniego elementu na liście głównej. Zobacz `AppendMenu` funkcję członkowską dla innych flag. `mtId`Element członkowski musi być pominięty ze struktury MENUITEMTEMPLATE, jeśli MF_POPUP jest określony w elemencie `mtOption` .

Miejsce przydzieloną dla struktury MENUITEMTEMPLATE musi być wystarczająco duże, aby można było `mtString` zawierać nazwę elementu menu jako ciąg zakończony znakiem null.

Przed wyjściem aplikacja musi zwolnić zasoby systemowe skojarzone z menu, jeśli menu nie jest przypisane do okna. Aplikacja zwolni menu, wywołując funkcję elementu członkowskiego [DestroyMenu](#destroymenu) .

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCWindowing#30](../../mfc/reference/codesnippet/cpp/cmenu-class_10.cpp)]

## <a name="cmenum_hmenu"></a><a name="m_hmenu"></a> CMenu:: m_hMenu

Określa dojście HMENU menu systemu Windows dołączonego do `CMenu` obiektu.

```
HMENU m_hMenu;
```

### <a name="example"></a>Przykład

  Zobacz przykład dla [CMenu:: LoadMenu](#loadmenu).

## <a name="cmenumeasureitem"></a><a name="measureitem"></a> CMenu::MeasureItem

Wywoływane przez platformę, gdy zostanie utworzony menu z stylem rysowania przez właściciela.

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>Parametry

*lpMeasureItemStruct*<br/>
Wskaźnik do `MEASUREITEMSTRUCT` struktury.

### <a name="remarks"></a>Uwagi

Domyślnie ta funkcja członkowska nic nie robi. Zastąp tę funkcję członkowską i wypełnij `MEASUREITEMSTRUCT` strukturę, aby informować okna o wymiarach menu.

Opis struktury można znaleźć w temacie [CWnd:: OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) `MEASUREITEMSTRUCT` .

### <a name="example"></a>Przykład

Następujący kod pochodzi z przykładu MFC [CTRLTEST](../../overview/visual-cpp-samples.md) :

[!code-cpp[NVC_MFCWindowing#31](../../mfc/reference/codesnippet/cpp/cmenu-class_11.cpp)]

## <a name="cmenumodifymenu"></a><a name="modifymenu"></a> CMenu::ModifyMenu

Zmienia istniejący element menu na pozycji określonej przez *npozycji*.

```
BOOL ModifyMenu(
    UINT nPosition,
    UINT nFlags,
    UINT_PTR nIDNewItem = 0,
    LPCTSTR lpszNewItem = NULL);

BOOL ModifyMenu(
    UINT nPosition,
    UINT nFlags,
    UINT_PTR nIDNewItem,
    const CBitmap* pBmp);
```

### <a name="parameters"></a>Parametry

*Npozycji*<br/>
Określa element menu, który ma zostać zmieniony. Parametr *nFlags* może służyć do interpretowania *npozycji* w następujący sposób:

|nFlags|Interpretacja Npozycji|
|------------|---------------------------------|
|MF_BYCOMMAND|Określa, że parametr zwraca identyfikator polecenia istniejącego elementu menu. Jest to wartość domyślna, jeśli nie MF_BYCOMMAND ani MF_BYPOSITION.|
|MF_BYPOSITION|Określa, że parametr podaje pozycję istniejącego elementu menu. Pierwszy element znajduje się na pozycji 0.|

*nFlags*<br/>
Określa sposób interpretowania *npozycji* i zawiera informacje o zmianach wprowadzonych w elemencie menu. Aby uzyskać listę flag, które mogą być ustawiane, zobacz funkcja członkowska [AppendMenu](#appendmenu) .

*nIDNewItem*<br/>
Określa identyfikator polecenia zmodyfikowanego elementu menu lub, jeśli *nFlags* jest ustawiony na MF_POPUP, uchwyt menu (HMENU) menu podręcznego. Parametr *nIDNewItem* jest ignorowany (niewymagane), jeśli *nFlags* jest ustawiony na MF_SEPARATOR.

*lpszNewItem*<br/>
Określa zawartość nowego elementu menu. Parametr *nFlags* może służyć do interpretowania *lpszNewItem* w następujący sposób:

|nFlags|Interpretacja lpszNewItem|
|------------|-----------------------------------|
|MF_OWNERDRAW|Zawiera wartość 32-bitowej dostarczonej przez aplikację, która może być używana przez aplikację do obsługi dodatkowych danych skojarzonych z elementem menu. Ta wartość 32-bitowa jest dostępna dla aplikacji podczas przetwarzania MF_MEASUREITEM i MF_DRAWITEM.|
|MF_STRING|Zawiera długi wskaźnik do ciągu zakończonego wartością null lub do `CString` .|
|MF_SEPARATOR|Parametr *lpszNewItem* jest ignorowany (niewymagany).|

*pBmp*<br/>
Wskazuje `CBitmap` obiekt, który będzie używany jako element menu.

### <a name="return-value"></a>Wartość zwracana

Różne od zera, jeśli funkcja zakończyła się pomyślnie; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Aplikacja określa nowy stan elementu menu przez ustawienie wartości w *nFlags*. Jeśli ta funkcja zastępuje menu podręczne skojarzone z elementem menu, niszczy stare menu wyskakujące i zwalnia pamięć używaną przez menu podręczne.

Gdy *nIDNewItem* określa menu wyskakującego, będzie częścią menu, w którym jest wstawiany. Jeśli to menu zostanie zniszczone, wstawione menu również zostanie zniszczone. Wstawione menu powinno być odłączone od obiektu, `CMenu` Aby uniknąć konfliktu.

Gdy zostanie zmienione menu znajdujące się w oknie (niezależnie od tego, czy okno jest wyświetlane), aplikacja powinna wywołać `CWnd::DrawMenuBar` . Aby zmienić atrybuty istniejących elementów menu, można znacznie szybciej używać `CheckMenuItem` `EnableMenuItem` funkcji i.

### <a name="example"></a>Przykład

  Zobacz przykład dla [CMenu:: InsertMenu](#insertmenu).

## <a name="cmenuoperator-hmenu"></a><a name="operator_hmenu"></a> CMenu:: operator HMENU

Użyj tego operatora, aby pobrać uchwyt `CMenu` obiektu.

```
operator HMENU() const;
```

### <a name="return-value"></a>Wartość zwracana

Jeśli to się powiedzie, dojście `CMenu` obiektu; w przeciwnym razie, wartość null.

### <a name="remarks"></a>Uwagi

Możesz użyć uchwytu, aby bezpośrednio wywołać interfejsy API systemu Windows.

## <a name="cmenuoperator-"></a><a name="operator_neq"></a> CMenu:: operator! =

Określa, czy dwa menu są logicznie nierówne.

```
BOOL operator!=(const CMenu& menu) const;
```

### <a name="parameters"></a>Parametry

*DodajMenu*<br/>
`CMenu`Obiekt do porównania.

### <a name="remarks"></a>Uwagi

Testuje, czy obiekt menu po lewej stronie nie jest równy obiektowi menu po prawej stronie.

## <a name="cmenuoperator-"></a><a name="operator_eq_eq"></a> CMenu:: operator = =

Określa, czy dwa menu są równe logiczne.

```
BOOL operator==(const CMenu& menu) const;
```

### <a name="parameters"></a>Parametry

*DodajMenu*<br/>
`CMenu`Obiekt do porównania.

### <a name="remarks"></a>Uwagi

Testuje, czy obiekt menu po lewej stronie jest równy (pod względem wartości HMENU) do obiektu menu po prawej stronie.

## <a name="cmenuremovemenu"></a><a name="removemenu"></a> CMenu::RemoveMenu

Usuwa element menu z menu podręcznym skojarzonego z menu.

```
BOOL RemoveMenu(
    UINT nPosition,
    UINT nFlags);
```

### <a name="parameters"></a>Parametry

*Npozycji*<br/>
Określa element menu, który ma zostać usunięty. Parametr *nFlags* może służyć do interpretowania *npozycji* w następujący sposób:

|nFlags|Interpretacja Npozycji|
|------------|---------------------------------|
|MF_BYCOMMAND|Określa, że parametr zwraca identyfikator polecenia istniejącego elementu menu. Jest to wartość domyślna, jeśli nie MF_BYCOMMAND ani MF_BYPOSITION.|
|MF_BYPOSITION|Określa, że parametr podaje pozycję istniejącego elementu menu. Pierwszy element znajduje się na pozycji 0.|

*nFlags*<br/>
Określa sposób interpretacji *npozycji* .

### <a name="return-value"></a>Wartość zwracana

Różne od zera, jeśli funkcja zakończyła się pomyślnie; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Nie niszczy dojścia menu wyskakującego, więc menu może być ponownie używane. Przed wywołaniem tej funkcji aplikacja może wywołać `GetSubMenu` funkcję członkowską, aby pobrać `CMenu` obiekt podręczny do ponownego użycia.

Gdy zostanie zmienione menu znajdujące się w oknie (niezależnie od tego, czy okno jest wyświetlane), aplikacja musi wywoływać `CWnd::DrawMenuBar` .

### <a name="example"></a>Przykład

  Zobacz przykład dla [CMenu:: InsertMenu](#insertmenu).

## <a name="cmenusetdefaultitem"></a><a name="setdefaultitem"></a> CMenu::SetDefaultItem

Ustawia domyślny element menu dla określonego menu.

```
BOOL SetDefaultItem(
    UINT uItem,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>Parametry

*uItem*<br/>
Identyfikator lub pozycja nowego domyślnego elementu menu lub-1 dla żadnego elementu domyślnego. Znaczenie tego parametru zależy od wartości *fByPos*.

*fByPos*<br/>
Wartość określająca znaczenie *uItem*. Jeśli ten parametr ma wartość FALSE, *uItem* jest identyfikatorem elementu menu. W przeciwnym razie jest to pozycja elementu menu.

### <a name="return-value"></a>Wartość zwracana

Jeśli funkcja się powiedzie, wartość zwracana jest różna od zera. Jeśli funkcja się nie powiedzie, zwracana wartość jest równa zero. Aby uzyskać rozszerzone informacje o błędach, należy użyć funkcji [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)systemu Win32, zgodnie z opisem w Windows SDK.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje zachowanie funkcji Win32 [SetMenuDefaultItem](/windows/win32/api/winuser/nf-winuser-setmenudefaultitem), zgodnie z opisem w Windows SDK.

### <a name="example"></a>Przykład

  Zobacz przykład dla [CMenu:: InsertMenu](#insertmenu).

## <a name="cmenusetmenucontexthelpid"></a><a name="setmenucontexthelpid"></a> CMenu::SetMenuContextHelpId

Kojarzy identyfikator pomocy kontekstowej z `CMenu` .

```
BOOL SetMenuContextHelpId(DWORD dwContextHelpId);
```

### <a name="parameters"></a>Parametry

*dwContextHelpId*<br/>
Identyfikator pomocy kontekstowej do skojarzenia z `CMenu` .

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie 0

### <a name="remarks"></a>Uwagi

Wszystkie elementy w menu korzystają z tego identyfikatora — nie można dołączyć identyfikatora kontekstu pomocy do poszczególnych elementów menu.

### <a name="example"></a>Przykład

  Zobacz przykład dla [CMenu:: InsertMenu](#insertmenu).

## <a name="cmenusetmenuinfo"></a><a name="setmenuinfo"></a> CMenu::SetMenuInfo

Ustawia informacje dla menu.

```
BOOL SetMenuInfo(LPCMENUINFO lpcmi);
```

### <a name="parameters"></a>Parametry

*lpcmi*<br/>
Wskaźnik do struktury [MENUINFO](/windows/win32/api/winuser/ns-winuser-menuinfo) zawierającej informacje dla menu.

### <a name="return-value"></a>Wartość zwracana

Jeśli funkcja się powiedzie, wartość zwracana jest różna od zera. w przeciwnym razie wartość zwracana jest równa zero.

### <a name="remarks"></a>Uwagi

Wywołaj tę funkcję, aby ustawić określone informacje na temat menu.

## <a name="cmenusetmenuitembitmaps"></a><a name="setmenuitembitmaps"></a> CMenu::SetMenuItemBitmaps

Kojarzy określone mapy bitowe z elementem menu.

```
BOOL SetMenuItemBitmaps(
    UINT nPosition,
    UINT nFlags,
    const CBitmap* pBmpUnchecked,
    const CBitmap* pBmpChecked);
```

### <a name="parameters"></a>Parametry

*Npozycji*<br/>
Określa element menu, który ma zostać zmieniony. Parametr *nFlags* może służyć do interpretowania *npozycji* w następujący sposób:

|nFlags|Interpretacja Npozycji|
|------------|---------------------------------|
|MF_BYCOMMAND|Określa, że parametr zwraca identyfikator polecenia istniejącego elementu menu. Jest to wartość domyślna, jeśli nie MF_BYCOMMAND ani MF_BYPOSITION.|
|MF_BYPOSITION|Określa, że parametr podaje pozycję istniejącego elementu menu. Pierwszy element znajduje się na pozycji 0.|

*nFlags*<br/>
Określa sposób interpretacji *npozycji* .

*pBmpUnchecked*<br/>
Określa mapę bitową, która ma być używana dla elementów menu, które nie są zaznaczone.

*pBmpChecked*<br/>
Określa mapę bitową, która ma być używana dla elementów menu, które są zaznaczone.

### <a name="return-value"></a>Wartość zwracana

Różne od zera, jeśli funkcja zakończyła się pomyślnie; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Niezależnie od tego, czy element menu jest zaznaczony, czy niezaznaczony, system Windows wyświetla odpowiednią mapę bitową obok elementu menu.

Jeśli *pBmpUnchecked* lub *pBmpChecked* ma wartość null, system Windows nie wyświetla niczego obok elementu menu dla odpowiadającego atrybutu. Jeśli oba parametry mają wartość NULL, system Windows używa domyślnego znacznika wyboru, gdy element jest zaznaczony i usuwa znacznik wyboru, gdy element jest niezaznaczony.

Gdy menu zostanie zniszczone, te mapy bitowe nie są niszczone; Aplikacja musi je zniszczyć.

Funkcja systemu Windows `GetMenuCheckMarkDimensions` Pobiera wymiary domyślnego znacznika wyboru używanego dla elementów menu. Aplikacja używa tych wartości, aby określić odpowiedni rozmiar map bitowych dostarczonych z tą funkcją. Pobierz rozmiar, Utwórz mapy bitowe, a następnie ustaw je.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCWindowing#32](../../mfc/reference/codesnippet/cpp/cmenu-class_12.cpp)]

[!code-cpp[NVC_MFCWindowing#33](../../mfc/reference/codesnippet/cpp/cmenu-class_13.cpp)]

## <a name="cmenusetmenuiteminfo"></a><a name="setmenuiteminfo"></a> CMenu::SetMenuItemInfo

Zmienia informacje o elemencie menu.

```
BOOL SetMenuItemInfo(
    UINT uItem,
    LPMENUITEMINFO lpMenuItemInfo,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>Parametry

*uItem*<br/>
Zobacz opis elementu *uItem* w [SetMenuItemInfo](/windows/win32/api/winuser/nf-winuser-setmenuiteminfow) w Windows SDK.

*lpMenuItemInfo*<br/>
Zobacz opis elementu *lpmii* w `SetMenuItemInfo` Windows SDK.

*fByPos*<br/>
Zobacz opis elementu *fByPosition* w `SetMenuItemInfo` Windows SDK.

### <a name="remarks"></a>Uwagi

Ta funkcja otacza [SetMenuItemInfo](/windows/win32/api/winuser/nf-winuser-setmenuiteminfow), opisane w Windows SDK.

## <a name="cmenutrackpopupmenu"></a><a name="trackpopupmenu"></a> CMenu::TrackPopupMenu

Wyświetla ruchome menu wyskakujące w określonej lokalizacji i śledzi wybór elementów z menu podręcznego.

```
BOOL TrackPopupMenu(
    UINT nFlags,
    int x,
    int y,
    CWnd* pWnd,
    LPCRECT lpRect = 0);
```

### <a name="parameters"></a>Parametry

*nFlags*<br/>
Określa flagi położenia ekranu i myszy. Zobacz [TrackPopupMenu](/windows/win32/api/winuser/nf-winuser-trackpopupmenu) , aby uzyskać listę dostępnych flag.

*x*<br/>
Określa położenie w poziomie we współrzędnych ekranu menu podręcznego. W zależności od wartości parametru *nFlags* menu może być wyrównane do lewej, wyrównane do prawej lub wyśrodkowane względem tego położenia.

*Y*<br/>
Określa położenie w pionie Współrzędne ekranu górnej krawędzi menu na ekranie.

*pWnd*<br/>
Identyfikuje okno, które jest właścicielem menu podręcznego. Ten parametr nie może mieć wartości NULL, nawet jeśli określono flagę TPM_NONOTIFY. To okno odbiera wszystkie WM_COMMAND komunikaty z menu. W systemie Windows w wersji 3,1 i nowszych okno nie odbiera WM_COMMAND komunikatów, dopóki nie `TrackPopupMenu` zwróci. W systemie Windows 3,0 okno odbiera WM_COMMAND komunikatów przed `TrackPopupMenu` zwróceniem.

*lpRect*<br/>
Ignorowane.

### <a name="return-value"></a>Wartość zwracana

Ta metoda zwraca wynik wywołania [TrackPopupMenu](/windows/win32/api/winuser/nf-winuser-trackpopupmenu) w Windows SDK.

### <a name="remarks"></a>Uwagi

Przestawne menu wyskakujące może znajdować się w dowolnym miejscu na ekranie.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCWindowing#34](../../mfc/reference/codesnippet/cpp/cmenu-class_14.cpp)]

## <a name="cmenutrackpopupmenuex"></a><a name="trackpopupmenuex"></a> CMenu::TrackPopupMenuEx

Wyświetla ruchome menu wyskakujące w określonej lokalizacji i śledzi wybór elementów z menu podręcznego.

```
BOOL TrackPopupMenuEx(
    UINT fuFlags,
    int x,
    int y,
    CWnd* pWnd,
    LPTPMPARAMS lptpm);
```

### <a name="parameters"></a>Parametry

*fuFlags*<br/>
Określa różne funkcje menu rozszerzonego. Aby uzyskać listę wszystkich wartości i ich znaczenie, zobacz [TrackPopupMenuEx](/windows/win32/api/winuser/nf-winuser-trackpopupmenuex).

*x*<br/>
Określa położenie w poziomie we współrzędnych ekranu menu podręcznego.

*Y*<br/>
Określa położenie w pionie Współrzędne ekranu górnej krawędzi menu na ekranie.

*pWnd*<br/>
Wskaźnik do okna będącego właścicielem menu podręcznego i otrzymującego komunikaty z utworzonego menu. To okno może być dowolnym oknem z bieżącej aplikacji, ale nie może mieć wartości NULL. Jeśli w parametrze *fuFlags* określono wartość TPM_NONOTIFY, funkcja nie będzie wysyłać żadnych komunikatów do *pWnd*. Funkcja musi zwrócić do okna wskazanego przez *pWnd* , aby otrzymać komunikat WM_COMMAND.

*lptpm*<br/>
Wskaźnik na strukturę [TPMPARAMS](/windows/win32/api/winuser/ns-winuser-tpmparams) , która określa obszar ekranu, którego menu nie powinno się nakładać. Ten parametr może mieć wartość NULL.

### <a name="return-value"></a>Wartość zwracana

W przypadku określenia TPM_RETURNCMD w parametrze *fuFlags* wartość zwracana jest identyfikatorem elementu menu elementu wybranego przez użytkownika. Jeśli użytkownik anuluje menu bez dokonania wyboru lub jeśli wystąpi błąd, zwracana wartość jest równa 0.

Jeśli nie określisz TPM_RETURNCMD w parametrze *fuFlags* , wartość zwracana jest różna od zera, jeśli funkcja się powiedzie i 0 w przypadku niepowodzenia. Aby uzyskać rozszerzone informacje o błędzie, wywołaj [wartość GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror).

### <a name="remarks"></a>Uwagi

Przestawne menu wyskakujące może znajdować się w dowolnym miejscu na ekranie. Aby uzyskać więcej informacji na temat obsługi błędów podczas tworzenia menu rozwijanego, zobacz [TrackPopupMenuEx](/windows/win32/api/winuser/nf-winuser-trackpopupmenuex).

## <a name="see-also"></a>Zobacz też

[Przykład CTRLTEST MFC](../../overview/visual-cpp-samples.md)<br/>
[Przykład DYNAMENU MFC](../../overview/visual-cpp-samples.md)<br/>
[Klasa CObject](../../mfc/reference/cobject-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa CObject](../../mfc/reference/cobject-class.md)

---
description: 'Dowiedz się więcej na temat: Klasa CUserToolsManager'
title: Klasa CUserToolsManager
ms.date: 11/04/2016
f1_keywords:
- CUserToolsManager
- AFXUSERTOOLSMANAGER/CUserToolsManager
- AFXUSERTOOLSMANAGER/CUserToolsManager::CUserToolsManager
- AFXUSERTOOLSMANAGER/CUserToolsManager::CreateNewTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::FindTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetArgumentsMenuID
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetDefExt
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetFilter
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetInitialDirMenuID
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetMaxTools
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetToolsEntryCmd
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetUserTools
- AFXUSERTOOLSMANAGER/CUserToolsManager::InvokeTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::IsUserToolCmd
- AFXUSERTOOLSMANAGER/CUserToolsManager::LoadState
- AFXUSERTOOLSMANAGER/CUserToolsManager::MoveToolDown
- AFXUSERTOOLSMANAGER/CUserToolsManager::MoveToolUp
- AFXUSERTOOLSMANAGER/CUserToolsManager::RemoveTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::SaveState
- AFXUSERTOOLSMANAGER/CUserToolsManager::SetDefExt
- AFXUSERTOOLSMANAGER/CUserToolsManager::SetFilter
helpviewer_keywords:
- CUserToolsManager [MFC], CUserToolsManager
- CUserToolsManager [MFC], CreateNewTool
- CUserToolsManager [MFC], FindTool
- CUserToolsManager [MFC], GetArgumentsMenuID
- CUserToolsManager [MFC], GetDefExt
- CUserToolsManager [MFC], GetFilter
- CUserToolsManager [MFC], GetInitialDirMenuID
- CUserToolsManager [MFC], GetMaxTools
- CUserToolsManager [MFC], GetToolsEntryCmd
- CUserToolsManager [MFC], GetUserTools
- CUserToolsManager [MFC], InvokeTool
- CUserToolsManager [MFC], IsUserToolCmd
- CUserToolsManager [MFC], LoadState
- CUserToolsManager [MFC], MoveToolDown
- CUserToolsManager [MFC], MoveToolUp
- CUserToolsManager [MFC], RemoveTool
- CUserToolsManager [MFC], SaveState
- CUserToolsManager [MFC], SetDefExt
- CUserToolsManager [MFC], SetFilter
ms.assetid: bdfa37ae-efca-4616-abb5-9d0dcd2d335b
ms.openlocfilehash: 1c6b3b6ec2912a0093929ac117d878d54ed9757f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344955"
---
# <a name="cusertoolsmanager-class"></a>Klasa CUserToolsManager

Utrzymuje kolekcję obiektów [klasy CUserTool](../../mfc/reference/cusertool-class.md) w aplikacji. Narzędzie użytkownika to element menu, w którym jest uruchamiana aplikacja zewnętrzna. `CUserToolsManager`Obiekt umożliwia użytkownikowi lub deweloperom Dodawanie nowych narzędzi użytkownika do aplikacji. Obsługuje wykonywanie poleceń skojarzonych z narzędziami użytkownika, a także zapisuje informacje o narzędziach użytkownika w rejestrze systemu Windows.

## <a name="syntax"></a>Składnia

```
class CUserToolsManager : public CObject
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CUserToolsManager::CUserToolsManager](#cusertoolsmanager)|Konstruuje a `CUserToolsManager` .|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CUserToolsManager::CreateNewTool](#createnewtool)|Tworzy nowe narzędzie użytkownika.|
|[CUserToolsManager::FindTool](#findtool)|Zwraca wskaźnik do `CMFCUserTool` obiektu, który jest skojarzony z określonym identyfikatorem polecenia.|
|[CUserToolsManager::GetArgumentsMenuID](#getargumentsmenuid)|Zwraca identyfikator zasobu skojarzony z menu **argumenty** na karcie **Narzędzia** okna dialogowego **Dostosowywanie** .|
|[CUserToolsManager::GetDefExt](#getdefext)|Zwraca domyślne rozszerzenie, które jest używane przez okno dialogowe **Otwórz plik** ( [CFileDialog](../../mfc/reference/cfiledialog-class.md#cfiledialog)) w polu **polecenie** na karcie **Narzędzia** okna dialogowego **Dostosowywanie** .|
|[CUserToolsManager:: getFilter](#getfilter)|Zwraca filtr plików, który jest wykorzystywany przez okno dialogowe **Otwórz plik** ( [Klasa CFileDialog](../../mfc/reference/cfiledialog-class.md)) w polu **polecenie** na karcie **Narzędzia** w oknie dialogowym **Dostosowywanie** .|
|[CUserToolsManager::GetInitialDirMenuID](#getinitialdirmenuid)|Zwraca identyfikator zasobu skojarzony z menu **początkowy katalog** na karcie **Narzędzia** okna dialogowego **Dostosowywanie** .|
|[CUserToolsManager::GetMaxTools](#getmaxtools)|Zwraca maksymalną liczbę narzędzi użytkownika, które można przydzielić w aplikacji.|
|[CUserToolsManager::GetToolsEntryCmd](#gettoolsentrycmd)|Zwraca identyfikator polecenia symbolu zastępczego elementu menu dla narzędzi użytkownika.|
|[CUserToolsManager::GetUserTools](#getusertools)|Zwraca odwołanie do listy narzędzi użytkownika.|
|[CUserToolsManager::InvokeTool](#invoketool)|Wykonuje aplikację skojarzoną z narzędziem użytkownika o określonym IDENTYFIKATORze polecenia.|
|[CUserToolsManager::IsUserToolCmd](#isusertoolcmd)|Określa, czy identyfikator polecenia jest skojarzony z narzędziem użytkownika.|
|[CUserToolsManager:: LoadState](#loadstate)|Ładuje informacje o narzędziach użytkownika z rejestru systemu Windows.|
|[CUserToolsManager::MoveToolDown](#movetooldown)|Przenosi określone narzędzie użytkownika w dół na liście narzędzi użytkownika.|
|[CUserToolsManager::MoveToolUp](#movetoolup)|Przenosi określone narzędzie użytkownika na liście narzędzi użytkownika.|
|[CUserToolsManager::RemoveTool](#removetool)|Usuwa określone narzędzie użytkownika z aplikacji.|
|[CUserToolsManager:: SaveState](#savestate)|Przechowuje informacje o narzędziach użytkownika w rejestrze systemu Windows.|
|[CUserToolsManager::SetDefExt](#setdefext)|Określa domyślne rozszerzenie, które jest używane przez okno dialogowe **Otwórz plik** ( [Klasa CFileDialog](../../mfc/reference/cfiledialog-class.md)) w polu **polecenie** na karcie **Narzędzia** w oknie dialogowym **Dostosowywanie** .|
|[CUserToolsManager:: setFilter](#setfilter)|Określa filtr pliku, który jest używane przez okno dialogowe **Otwórz plik** ( [Klasa CFileDialog](../../mfc/reference/cfiledialog-class.md)) w polu **polecenie** na karcie **Narzędzia** w oknie dialogowym **Dostosowywanie** .|

## <a name="remarks"></a>Uwagi

Aby dołączyć narzędzia użytkownika do aplikacji, musisz:

1. Zarezerwuj element menu i skojarzony identyfikator polecenia dla wpisu menu narzędzia użytkownika.

2. Zarezerwuj sekwencyjny identyfikator polecenia dla każdego narzędzia użytkownika, które użytkownik może zdefiniować w aplikacji.

3. Wywołaj metodę [CWinAppEx:: EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) i podaj następujące parametry: ID polecenia menu, identyfikator polecenia narzędzia User ID i ostatni identyfikator polecenia narzędzia użytkownika.

Dla każdej aplikacji powinien istnieć tylko jeden `CUserToolsManager` obiekt globalny.

Aby zapoznać się z przykładem narzędzi użytkownika, zobacz przykładowy projekt VisualStudioDemo.

## <a name="example"></a>Przykład

W poniższym przykładzie pokazano, jak pobrać odwołanie do `CUserToolsManager` obiektu i jak utworzyć nowe narzędzia użytkownika. Ten fragment kodu jest częścią [przykładu demonstracyjnego Visual Studio](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_VisualStudioDemo#38](../../mfc/codesnippet/cpp/cusertoolsmanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

`CUserToolsManager`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxusertoolsmanager. h

## <a name="cusertoolsmanagercreatenewtool"></a><a name="createnewtool"></a> CUserToolsManager::CreateNewTool

Tworzy nowe narzędzie użytkownika.

```
CUserTool* CreateNewTool();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do nowo utworzonego narzędzia użytkownika lub wartość NULL, jeśli liczba narzędzi użytkownika przekroczyła wartość maksymalną. Zwracany typ jest taki sam jak typ, który jest przesyłany do `CWinAppEx::EnableUserTools` jako parametr *pToolRTC* .

### <a name="remarks"></a>Uwagi

Ta metoda umożliwia znalezienie pierwszego dostępnego polecenia menu w zakresie, który jest podany w wywołaniu [CWinAppEx:: EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) i przypisuje narzędzie użytkownika tego identyfikatora.

Metoda kończy się niepowodzeniem, jeśli liczba narzędzi osiągnęła wartość maksymalną. Dzieje się tak, gdy wszystkie identyfikatory poleceń w zakresie są przypisane do narzędzi użytkownika. Maksymalną liczbę narzędzi można pobrać, wywołując [CUserToolsManager:: GetMaxTools](#getmaxtools). Dostęp do listy narzędzi można uzyskać, wywołując metodę [CUserToolsManager:: GetUserTools](#getusertools) .

## <a name="cusertoolsmanagercusertoolsmanager"></a><a name="cusertoolsmanager"></a> CUserToolsManager::CUserToolsManager

Konstruuje a `CUserToolsManager` . Każda aplikacja musi mieć co najwyżej jednego Menedżera narzędzi użytkownika.

```
CUserToolsManager();

CUserToolsManager(
    const UINT uiCmdToolsDummy,
    const UINT uiCmdFirst,
    const UINT uiCmdLast,
    CRuntimeClass* pToolRTC=RUNTIME_CLASS(CUserTool),
    UINT uArgMenuID=0,
    UINT uInitDirMenuID=0);
```

### <a name="parameters"></a>Parametry

*uiCmdToolsDummy*<br/>
podczas Liczba całkowita bez znaku, która jest stosowana przez środowisko jako symbol zastępczy dla identyfikatora polecenia menu narzędzia użytkownika.

*uiCmdFirst*<br/>
podczas Identyfikator polecenia pierwszego narzędzia użytkownika.

*uiCmdLast*<br/>
podczas Identyfikator polecenia dla ostatniego polecenia narzędzia użytkownika.

*pToolRTC*<br/>
podczas Klasa, którą tworzy [CUserToolsManager:: CreateNewTool](#createnewtool) . Korzystając z tej klasy, można użyć pochodnego typu [klasy CUserTool](../../mfc/reference/cusertool-class.md) zamiast domyślnej implementacji.

*uArgMenuID*<br/>
podczas Identyfikator zasobu menu podręcznego menu argumentów.

*uInitDirMenuID*<br/>
podczas Menu Identyfikator zasobu menu podręcznego katalogu początkowego.

### <a name="remarks"></a>Uwagi

Nie wywołuj tego konstruktora. Zamiast tego wywołaj [CWinAppEx:: EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) , aby włączyć narzędzia użytkownika, a następnie Wywołaj [CWinAppEx:: GetUserToolsManager](../../mfc/reference/cwinappex-class.md#getusertoolsmanager) , aby uzyskać wskaźnik do elementu `CUserToolsManager` . Aby uzyskać więcej informacji, zobacz [Narzędzia zdefiniowane przez użytkownika](../../mfc/user-defined-tools.md).

## <a name="cusertoolsmanagerfindtool"></a><a name="findtool"></a> CUserToolsManager::FindTool

Zwraca wskaźnik do obiektu [klasy CUserTool](../../mfc/reference/cusertool-class.md) , który jest skojarzony z określonym identyfikatorem polecenia.

```
CUserTool* FindTool(UINT uiCmdId) const;
```

### <a name="parameters"></a>Parametry

*uiCmdId*<br/>
podczas Identyfikator polecenia menu.

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do [klasy CUserTool](../../mfc/reference/cusertool-class.md) lub `CUserTool` obiektu pochodnego w razie sukcesu; w przeciwnym razie wartość null.

### <a name="remarks"></a>Uwagi

Gdy `FindTool` to się powiedzie, zwracany typ jest taki sam jak typ parametru *PToolRTC* do [CWinAppEx:: EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools).

## <a name="cusertoolsmanagergetargumentsmenuid"></a><a name="getargumentsmenuid"></a> CUserToolsManager::GetArgumentsMenuID

Zwraca identyfikator zasobu skojarzony z menu **argumenty** na karcie **Narzędzia** okna dialogowego **Dostosowywanie** .

```
UINT GetArgumentsMenuID() const;
```

### <a name="return-value"></a>Wartość zwracana

Identyfikator zasobu menu.

### <a name="remarks"></a>Uwagi

*UArgMenuID* parametr [CWinAppEx:: EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) określa identyfikator zasobu.

## <a name="cusertoolsmanagergetdefext"></a><a name="getdefext"></a> CUserToolsManager::GetDefExt

Zwraca domyślne rozszerzenie, które jest używane przez okno dialogowe **Otwórz plik** ( [CFileDialog](../../mfc/reference/cfiledialog-class.md#cfiledialog)) w polu **polecenie** na karcie **Narzędzia** okna dialogowego **Dostosowywanie** .

```
const CString& GetDefExt() const;
```

### <a name="return-value"></a>Wartość zwracana

Odwołanie do `CString` obiektu, który zawiera rozszerzenie.

## <a name="cusertoolsmanagergetfilter"></a><a name="getfilter"></a> CUserToolsManager:: getFilter

Zwraca filtr plików, który jest wykorzystywany przez okno dialogowe **Otwórz plik** ( [Klasa CFileDialog](../../mfc/reference/cfiledialog-class.md)) w polu **polecenie** na karcie **Narzędzia** w oknie dialogowym **Dostosowywanie** .

```
const CString& GetFilter() const;
```

### <a name="return-value"></a>Wartość zwracana

Odwołanie do `CString` obiektu, który zawiera filtr.

## <a name="cusertoolsmanagergetinitialdirmenuid"></a><a name="getinitialdirmenuid"></a> CUserToolsManager::GetInitialDirMenuID

Zwraca identyfikator zasobu skojarzony z menu **początkowy katalog** na karcie **Narzędzia** okna dialogowego **Dostosowywanie** .

```
UINT GetInitialDirMenuID() const;
```

### <a name="return-value"></a>Wartość zwracana

Identyfikator zasobu menu.

### <a name="remarks"></a>Uwagi

Zwrócony identyfikator jest określony w parametrze *uInitDirMenuID* elementu [CWinAppEx:: EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools).

## <a name="cusertoolsmanagergetmaxtools"></a><a name="getmaxtools"></a> CUserToolsManager::GetMaxTools

Zwraca maksymalną liczbę narzędzi użytkownika, które można przydzielić w aplikacji.

```
int GetMaxTools() const;
```

### <a name="return-value"></a>Wartość zwracana

Maksymalna liczba narzędzi użytkownika, które można przydzielić.

### <a name="remarks"></a>Uwagi

Wywołaj tę metodę, aby pobrać maksymalną liczbę narzędzi, które mogą być przydzieloną w aplikacji. Ta liczba to liczba identyfikatorów z zakresu od *uiCmdFirst* do *uiCmdLast* parametrów przekazywanych do [CWinAppEx:: EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools).

## <a name="cusertoolsmanagergettoolsentrycmd"></a><a name="gettoolsentrycmd"></a> CUserToolsManager::GetToolsEntryCmd

Zwraca identyfikator polecenia symbolu zastępczego elementu menu dla narzędzi użytkownika.

```
UINT GetToolsEntryCmd() const;
```

### <a name="return-value"></a>Wartość zwracana

Identyfikator polecenia symbolu zastępczego.

### <a name="remarks"></a>Uwagi

Aby włączyć narzędzia użytkownika, należy wywołać [CWinAppEx:: EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools). Parametr *uiCmdToolsDummy* określa identyfikator polecenia poleceń narzędzi. Ta metoda zwraca identyfikator polecenia narzędzi. Wszędzie tam, gdzie ten identyfikator jest używany w menu, zostanie zastąpiony przez listę narzędzi użytkownika po wyświetleniu menu.

## <a name="cusertoolsmanagergetusertools"></a><a name="getusertools"></a> CUserToolsManager::GetUserTools

Zwraca odwołanie do listy narzędzi użytkownika.

```
const CObList& GetUserTools() const;
```

### <a name="return-value"></a>Wartość zwracana

Stałe odwołanie do obiektu [klasy CObList](../../mfc/reference/coblist-class.md) , który zawiera listę narzędzi użytkownika.

### <a name="remarks"></a>Uwagi

Wywołaj tę metodę, aby pobrać listę narzędzi użytkownika, które obsługuje obiekt [CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md) . Każde narzędzie użytkownika jest reprezentowane przez obiekt typu [CUserTool Class](../../mfc/reference/cusertool-class.md) lub typ pochodzący od `CUserTool` . Typ jest określany przez parametr *pToolRTC* w przypadku wywołania [CWinAppEx:: EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) w celu włączenia narzędzi użytkownika.

## <a name="cusertoolsmanagerinvoketool"></a><a name="invoketool"></a> CUserToolsManager::InvokeTool

Wykonuje aplikację skojarzoną z narzędziem użytkownika o określonym IDENTYFIKATORze polecenia.

```
BOOL InvokeTool(UINT uiCmdId);
```

### <a name="parameters"></a>Parametry

*uiCmdId*<br/>
podczas Identyfikator polecenia menu skojarzonego z narzędziem użytkownika.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli polecenie skojarzone z narzędziem użytkownika zostało wykonane pomyślnie; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Wywołaj tę metodę, aby wykonać aplikację skojarzoną z narzędziem użytkownika o IDENTYFIKATORze polecenia określonym przez *uiCmdId*.

## <a name="cusertoolsmanagerisusertoolcmd"></a><a name="isusertoolcmd"></a> CUserToolsManager::IsUserToolCmd

Określa, czy identyfikator polecenia jest skojarzony z narzędziem użytkownika.

```
BOOL IsUserToolCmd(UINT uiCmdId) const;
```

### <a name="parameters"></a>Parametry

*uiCmdId*<br/>
podczas Identyfikator polecenia elementu menu.

### <a name="return-value"></a>Wartość zwracana

Różne od zera, jeśli dany identyfikator polecenia jest skojarzony z narzędziem użytkownika; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Ta metoda sprawdza, czy dany identyfikator polecenia znajduje się w zakresie identyfikatora polecenia. Zakres należy określić podczas wywoływania [CWinAppEx:: EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) w celu włączenia narzędzi użytkownika.

## <a name="cusertoolsmanagerloadstate"></a><a name="loadstate"></a> CUserToolsManager:: LoadState

Ładuje informacje o narzędziach użytkownika z rejestru systemu Windows.

```
BOOL LoadState(LPCTSTR lpszProfileName=NULL);
```

### <a name="parameters"></a>Parametry

*lpszProfileName*<br/>
podczas Ścieżka klucza rejestru systemu Windows.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli stan został pomyślnie załadowany; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Ta metoda ładuje stan `CUserToolsManager` obiektu z rejestru systemu Windows.

Zazwyczaj ta metoda nie jest wywoływana bezpośrednio. [CWinAppEx:: LoadState](../../mfc/reference/cwinappex-class.md#loadstate) wywołuje go jako część procesu inicjowania obszaru roboczego.

## <a name="cusertoolsmanagermovetooldown"></a><a name="movetooldown"></a> CUserToolsManager::MoveToolDown

Przenosi określone narzędzie użytkownika w dół na liście narzędzi użytkownika.

```
BOOL MoveToolDown(CUserTool* pTool);
```

### <a name="parameters"></a>Parametry

*pTool*<br/>
podczas Określa narzędzie użytkownika do przeniesienia.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli narzędzie użytkownika zostało pomyślnie przeniesione w dół; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Metoda kończy się niepowodzeniem, jeśli narzędzie, które *pTool* określa, nie znajduje się na liście wewnętrznej lub jeśli narzędzie jest ostatnio na liście.

## <a name="cusertoolsmanagermovetoolup"></a><a name="movetoolup"></a> CUserToolsManager::MoveToolUp

Przenosi określone narzędzie użytkownika na liście narzędzi użytkownika.

```
BOOL MoveToolUp(CUserTool* pTool);
```

### <a name="parameters"></a>Parametry

*pTool*<br/>
podczas Określa narzędzie użytkownika do przeniesienia.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli narzędzie użytkownika zostało pomyślnie przeniesione; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Metoda kończy się niepowodzeniem, jeśli narzędzie, którego parametr *pTool* określa, nie znajduje się na liście wewnętrznej lub jeśli narzędzie jest pierwszym elementem narzędzia na liście.

## <a name="cusertoolsmanagerremovetool"></a><a name="removetool"></a> CUserToolsManager::RemoveTool

Usuwa określone narzędzie użytkownika z aplikacji.

```
BOOL RemoveTool(CUserTool* pTool);
```

### <a name="parameters"></a>Parametry

*pTool*<br/>
[in. out] Wskaźnik do narzędzia użytkownika do usunięcia.

### <a name="return-value"></a>Wartość zwracana

Ma wartość TRUE, jeśli narzędzie zostało pomyślnie usunięte. W przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Po pomyślnym usunięciu narzędzia ta metoda usuwa *pTool*.

## <a name="cusertoolsmanagersavestate"></a><a name="savestate"></a> CUserToolsManager:: SaveState

Przechowuje informacje o narzędziach użytkownika w rejestrze systemu Windows.

```
BOOL SaveState(LPCTSTR lpszProfileName=NULL);
```

### <a name="parameters"></a>Parametry

*lpszProfileName*<br/>
podczas Ścieżka do klucza rejestru systemu Windows.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli stan został pomyślnie zapisany; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Metoda przechowuje bieżący stan `CUserToolsManager` obiektu w rejestrze systemu Windows.

Zazwyczaj nie trzeba wywoływać tej metody bezpośrednio, [CWinAppEx:: SaveState](../../mfc/reference/cwinappex-class.md#savestate) wywołuje ją automatycznie jako część procesu serializacji obszaru roboczego aplikacji.

## <a name="cusertoolsmanagersetdefext"></a><a name="setdefext"></a> CUserToolsManager::SetDefExt

Określa domyślne rozszerzenie, które jest używane przez okno dialogowe **Otwórz plik** ( [Klasa CFileDialog](../../mfc/reference/cfiledialog-class.md)) w polu **polecenie** na karcie **Narzędzia** w oknie dialogowym **Dostosowywanie** .

```cpp
void SetDefExt(const CString& strDefExt);
```

### <a name="parameters"></a>Parametry

*strDefExt*<br/>
podczas Ciąg tekstowy, który zawiera domyślne rozszerzenie nazwy pliku.

### <a name="remarks"></a>Uwagi

Wywołaj tę metodę, aby określić domyślne rozszerzenie nazwy pliku w oknie dialogowym **otwieranie pliku** , które jest wyświetlane, gdy użytkownik wybierze aplikację do skojarzenia z narzędziem użytkownika. Wartość domyślna to "exe".

## <a name="cusertoolsmanagersetfilter"></a><a name="setfilter"></a> CUserToolsManager:: setFilter

Określa filtr pliku, który jest używane przez okno dialogowe **Otwórz plik** ( [Klasa CFileDialog](../../mfc/reference/cfiledialog-class.md)) w polu **polecenie** na karcie **Narzędzia** w oknie dialogowym **Dostosowywanie** .

```cpp
void SetFilter(const CString& strFilter);
```

### <a name="parameters"></a>Parametry

*strFilter*<br/>
podczas Określa filtr.

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CWinAppEx](../../mfc/reference/cwinappex-class.md)<br/>
[Klasa CUserTool](../../mfc/reference/cusertool-class.md)

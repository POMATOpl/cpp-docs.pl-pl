---
description: 'Dowiedz się więcej na temat: Klasa CMouseManager'
title: Klasa CMouseManager
ms.date: 11/04/2016
f1_keywords:
- CMouseManager
- AFXMOUSEMANAGER/CMouseManager
- AFXMOUSEMANAGER/CMouseManager::AddView
- AFXMOUSEMANAGER/CMouseManager::GetViewDblClickCommand
- AFXMOUSEMANAGER/CMouseManager::GetViewIconId
- AFXMOUSEMANAGER/CMouseManager::GetViewIdByName
- AFXMOUSEMANAGER/CMouseManager::GetViewNames
- AFXMOUSEMANAGER/CMouseManager::LoadState
- AFXMOUSEMANAGER/CMouseManager::SaveState
- AFXMOUSEMANAGER/CMouseManager::SetCommandForDblClk
helpviewer_keywords:
- CMouseManager [MFC], AddView
- CMouseManager [MFC], GetViewDblClickCommand
- CMouseManager [MFC], GetViewIconId
- CMouseManager [MFC], GetViewIdByName
- CMouseManager [MFC], GetViewNames
- CMouseManager [MFC], LoadState
- CMouseManager [MFC], SaveState
- CMouseManager [MFC], SetCommandForDblClk
ms.assetid: a4d05017-4e44-4a40-8b57-4ece0de20481
ms.openlocfilehash: 9816583aa9d05b76f97f1be1487898b5827fbcae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331555"
---
# <a name="cmousemanager-class"></a>Klasa CMouseManager

Zezwala użytkownikowi na kojarzenie różnych poleceń z określonym obiektem [CView](../../mfc/reference/cview-class.md) , gdy użytkownik kliknie dwukrotnie w tym widoku.

## <a name="syntax"></a>Składnia

```
class CMouseManager : public CObject
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMouseManager:: AddView](#addview)|Dodaje `CView` obiekt do okna dialogowego **Dostosowywanie** . Okno dialogowe **dostosowanie** umożliwia użytkownikowi skojarzenie dwukrotnego kliknięcia z poleceniem dla każdego z wymienionych widoków.|
|[CMouseManager::GetViewDblClickCommand](#getviewdblclickcommand)|Zwraca polecenie, które jest wykonywane, gdy użytkownik kliknie dwukrotnie w podanym widoku.|
|[CMouseManager::GetViewIconId](#getviewiconid)|Zwraca ikonę skojarzoną z danym IDENTYFIKATORem widoku.|
|[CMouseManager::GetViewIdByName](#getviewidbyname)|Zwraca identyfikator widoku skojarzony z podaną nazwą widoku.|
|[CMouseManager::GetViewNames](#getviewnames)|Pobiera listę wszystkich dodanych nazw widoków.|
|[CMouseManager:: LoadState](#loadstate)|Ładuje `CMouseManager` stan z rejestru systemu Windows.|
|[CMouseManager:: SaveState](#savestate)|Zapisuje `CMouseManager` stan w rejestrze systemu Windows.|
|[CMouseManager::SetCommandForDblClk](#setcommandfordblclk)|Kojarzy podane polecenie i podany widok.|

## <a name="remarks"></a>Uwagi

`CMouseManager`Klasa przechowuje kolekcję `CView` obiektów. Każdy widok jest identyfikowany przez nazwę i identyfikator. Te widoki są wyświetlane w oknie dialogowym **dostosowywania** . Użytkownik może zmienić polecenie skojarzone z dowolnym widokiem za pomocą okna dialogowego **Dostosowywanie** . Skojarzone polecenie jest wykonywane, gdy użytkownik kliknie dwukrotnie w tym widoku. Aby można było obsługiwać ten element z perspektywy kodowania, należy przetworzyć komunikat WM_LBUTTONDBLCLK i wywołać funkcję [CWinAppEx:: OnViewDoubleClick](../../mfc/reference/cwinappex-class.md#onviewdoubleclick) w kodzie dla tego `CView` obiektu.

Nie należy tworzyć `CMouseManager` obiektu ręcznie. Zostanie on utworzony przez strukturę aplikacji. Zostanie ona również zniszczona automatycznie, gdy użytkownik zakończy działanie aplikacji. Aby uzyskać wskaźnik do Menedżera myszy dla aplikacji, wywołaj [CWinAppEx:: GetMouseManager](../../mfc/reference/cwinappex-class.md#getmousemanager).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

`CMouseManager`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxmousemanager. h

## <a name="cmousemanageraddview"></a><a name="addview"></a> CMouseManager:: AddView

Rejestruje obiekt [CView](../../mfc/reference/cview-class.md) z [klasą CMouseManager](../../mfc/reference/cmousemanager-class.md) w celu obsługi niestandardowego zachowania myszy.

```
BOOL AddView(
    int iViewId,
    UINT uiViewNameResId,
    UINT uiIconId = 0);

BOOL AddView(
    int iId,
    LPCTSTR lpszViewName,
    UINT uiIconId = 0);
```

### <a name="parameters"></a>Parametry

*iViewId*<br/>
podczas Identyfikator widoku.

*uiViewNameResId*<br/>
podczas Identyfikator ciągu zasobu, który odwołuje się do nazwy widoku.

*uiIconId*<br/>
podczas Identyfikator ikony widoku.

*iId*<br/>
podczas Identyfikator widoku.

*lpszViewName*<br/>
podczas Nazwa widoku.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Aby można było obsługiwać niestandardowe zachowanie myszy, widok musi być zarejestrowany przy użyciu `CMouseManager` obiektu. Każdy obiekt pochodny `CView` klasy może być zarejestrowany za pomocą Menedżera myszy. Ciąg i ikona skojarzone z widokiem są wyświetlane na karcie **myszy** okna dialogowego **Dostosowywanie** .

Programista może tworzyć i obsługiwać identyfikatory widoków, takie jak *iViewId* i *IID*.

Aby uzyskać więcej informacji na temat zapewniania niestandardowego zachowania myszy, zobacz [Dostosowywanie klawiatury i myszy](../../mfc/keyboard-and-mouse-customization.md).

### <a name="example"></a>Przykład

W poniższym przykładzie pokazano, jak pobrać wskaźnik do `CMouseManager` obiektu za pomocą `CWinAppEx::GetMouseManager` metody i `AddView` metody w `CMouseManager` klasie. Ten fragment kodu jest częścią [przykładu kolekcji Stanów](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_StateCollection#4](../../mfc/reference/codesnippet/cpp/cmousemanager-class_1.cpp)]

## <a name="cmousemanagergetviewdblclickcommand"></a><a name="getviewdblclickcommand"></a> CMouseManager::GetViewDblClickCommand

Zwraca polecenie, które jest wykonywane, gdy użytkownik kliknie dwukrotnie w podanym widoku.

```
UINT GetViewDblClickCommand(int iId) const;
```

### <a name="parameters"></a>Parametry

*iId*<br/>
podczas Identyfikator widoku.

### <a name="return-value"></a>Wartość zwracana

Identyfikator polecenia, jeśli widok jest skojarzony z poleceniem; w przeciwnym razie 0.

## <a name="cmousemanagergetviewiconid"></a><a name="getviewiconid"></a> CMouseManager::GetViewIconId

Pobiera ikonę skojarzoną z IDENTYFIKATORem widoku.

```
UINT GetViewIconId(int iViewId) const;
```

### <a name="parameters"></a>Parametry

*iViewId*<br/>
podczas Identyfikator widoku.

### <a name="return-value"></a>Wartość zwracana

Identyfikator zasobu ikony, jeśli to się powiedzie; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Ta metoda zakończy się niepowodzeniem, jeśli widok nie jest najpierw zarejestrowany przy użyciu [CMouseManager:: AddView](#addview).

## <a name="cmousemanagergetviewidbyname"></a><a name="getviewidbyname"></a> CMouseManager::GetViewIdByName

Pobiera identyfikator widoku skojarzony z nazwą widoku.

```
int GetViewIdByName(LPCTSTR lpszName) const;
```

### <a name="parameters"></a>Parametry

*lpszName*<br/>
podczas Nazwa widoku.

### <a name="return-value"></a>Wartość zwracana

Identyfikator widoku, jeśli powodzenie; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Ta metoda przeszukuje widoki zarejestrowane przy użyciu [CMouseManager:: AddView](#addview).

## <a name="cmousemanagergetviewnames"></a><a name="getviewnames"></a> CMouseManager::GetViewNames

Pobiera listę wszystkich zarejestrowanych nazw widoków.

```cpp
void GetViewNames(CStringList& listOfNames) const;
```

### <a name="parameters"></a>Parametry

*listOfNames*<br/>
określoną Odwołanie do `CStringList` obiektu.

### <a name="remarks"></a>Uwagi

Ta metoda wypełnia parametr `listOfNames` nazwami wszystkich widoków zarejestrowanych przy użyciu [CMouseManager:: AddView](#addview).

## <a name="cmousemanagerloadstate"></a><a name="loadstate"></a> CMouseManager:: LoadState

Ładuje stan [klasy CMouseManager](../../mfc/reference/cmousemanager-class.md) z rejestru.

```
BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>Parametry

*lpszProfileName*<br/>
podczas Ścieżka klucza rejestru.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Informacje o stanie załadowane z rejestru obejmują zarejestrowane widoki, identyfikatory widoków i skojarzone polecenia. Jeśli parametr *lpszProfileName* ma wartość null, ta funkcja wczytuje `CMouseManager` dane z domyślnej lokalizacji rejestru kontrolowanej przez [klasę CWinAppEx](../../mfc/reference/cwinappex-class.md).

W większości przypadków nie jest konieczne bezpośrednie wywoływanie tej funkcji. Jest on wywoływany jako część procesu inicjowania obszaru roboczego. Aby uzyskać więcej informacji na temat procesu inicjowania obszaru roboczego, zobacz [CWinAppEx:: LoadState](../../mfc/reference/cwinappex-class.md#loadstate).

## <a name="cmousemanagersavestate"></a><a name="savestate"></a> CMouseManager:: SaveState

Zapisuje stan [klasy CMouseManager](../../mfc/reference/cmousemanager-class.md) w rejestrze.

```
BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>Parametry

*lpszProfileName*<br/>
podczas Ścieżka klucza rejestru.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Informacje o stanie zapisywane w rejestrze obejmują wszystkie zarejestrowane widoki, identyfikatory widoków i skojarzone polecenia. Jeśli parametr *lpszProfileName* ma wartość null, ta funkcja zapisuje `CMouseManager` dane do domyślnej lokalizacji rejestru kontrolowanej przez [klasę CWinAppEx](../../mfc/reference/cwinappex-class.md).

W większości przypadków nie jest konieczne bezpośrednie wywoływanie tej funkcji. Jest on wywoływany jako część procesu serializacji obszaru roboczego. Aby uzyskać więcej informacji na temat procesu serializacji obszaru roboczego, zobacz [CWinAppEx:: SaveState](../../mfc/reference/cwinappex-class.md#savestate).

## <a name="cmousemanagersetcommandfordblclk"></a><a name="setcommandfordblclk"></a> CMouseManager::SetCommandForDblClk

Kojarzy polecenie niestandardowe z widokiem, który jest po raz pierwszy zarejestrowany w Menedżerze myszy.

```cpp
void SetCommandForDblClk(
    int iViewId,
    UINT uiCmd);
```

### <a name="parameters"></a>Parametry

*iViewId*<br/>
podczas Identyfikator widoku.

*uiCmd*<br/>
podczas Identyfikator polecenia.

### <a name="remarks"></a>Uwagi

Aby skojarzyć polecenie niestandardowe z widokiem, należy najpierw zarejestrować widok przy użyciu [CMouseManager:: AddView](#addview). `AddView`Metoda wymaga identyfikatora widoku jako parametru wejściowego. Po zarejestrowaniu widoku można wywołać `CMouseManager::SetCommandForDblClk` przy użyciu tego samego parametru wejściowego identyfikatora widoku, który został dostarczony do `AddView` . Następnie, gdy użytkownik kliknie dwukrotnie mysz w zarejestrowanym widoku, aplikacja wykona polecenie wskazywane przez *uiCmd.* Aby zapewnić obsługę niestandardowego zachowania myszy, należy również dostosować widok zarejestrowany za pomocą Menedżera myszy. Aby uzyskać więcej informacji na temat niestandardowego zachowania myszy, zobacz [Dostosowywanie klawiatury i myszy](../keyboard-and-mouse-customization.md).

Jeśli wartość *uiCmd* jest równa 0, określony widok nie jest już skojarzony z poleceniem.

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CWinAppEx](../../mfc/reference/cwinappex-class.md)<br/>
[Dostosowywanie klawiatury i myszy](../../mfc/keyboard-and-mouse-customization.md)

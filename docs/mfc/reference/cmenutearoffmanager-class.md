---
description: 'Dowiedz się więcej na temat: Klasa CMenuTearOffManager'
title: Klasa CMenuTearOffManager
ms.date: 10/18/2018
f1_keywords:
- CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Build
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::GetRegPath
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Initialize
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::IsDynamicID
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Parse
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Reset
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::SetInUse
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::SetupTearOffMenus
helpviewer_keywords:
- CMenuTearOffManager [MFC], CMenuTearOffManager
- CMenuTearOffManager [MFC], Build
- CMenuTearOffManager [MFC], GetRegPath
- CMenuTearOffManager [MFC], Initialize
- CMenuTearOffManager [MFC], IsDynamicID
- CMenuTearOffManager [MFC], Parse
- CMenuTearOffManager [MFC], Reset
- CMenuTearOffManager [MFC], SetInUse
- CMenuTearOffManager [MFC], SetupTearOffMenus
ms.assetid: ab7ca272-ce42-4678-95f7-6ad75038f5a0
ms.openlocfilehash: b80f2e935f8d1dd47bf19a11522e4556b35490b4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336647"
---
# <a name="cmenutearoffmanager-class"></a>Klasa CMenuTearOffManager

Zarządza menu odrywania. Menu odrywania jest menu na pasku menu. Użytkownik może usunąć menu odrywania z paska menu, co spowoduje, że menu odrywania jest zmiennoprzecinkowe.

   Aby uzyskać więcej szczegółów, zobacz kod źródłowy znajdujący się w folderze **VC \\ atlmfc \\ src \\ MFC** instalacji programu Visual Studio.

## <a name="syntax"></a>Składnia

```
class CMenuTearOffManager : public CObject
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMenuTearOffManager::CMenuTearOffManager](#cmenutearoffmanager)|Konstruuje `CMenuTearOffManager` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMenuTearOffManager:: Build](#build)||
|[CMenuTearOffManager::GetRegPath](#getregpath)||
|[CMenuTearOffManager:: Initialize](#initialize)|Inicjuje `CMenuTearOffManager` obiekt.|
|[CMenuTearOffManager::IsDynamicID](#isdynamicid)||
|[CMenuTearOffManager::P arse](#parse)||
|[CMenuTearOffManager:: Reset](#reset)||
|[CMenuTearOffManager::SetInUse](#setinuse)||
|[CMenuTearOffManager::SetupTearOffMenus](#setuptearoffmenus)||

## <a name="remarks"></a>Uwagi

Aby można było używać menu rozrywania w aplikacji, musisz mieć `CMenuTearOffManager` obiekt. W większości przypadków nie utworzysz ani nie zainicjujesz `CMenuTearOffManager` obiektu bezpośrednio. Jest to obsługiwane w przypadku wywołania funkcji [CWinAppEx:: EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus) .

## <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób konstruowania i inicjowania `CMenuTearOffManager` obiektu przez wywołanie `CWinAppEX::EnableTearOffMenus` metody. Ten fragment kodu jest częścią [przykładu Notatnika programu Word](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_WordPad#12](../../mfc/reference/codesnippet/cpp/cmenutearoffmanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

`CMenuTearOffManager`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxmenutearoffmanager. h

## <a name="cmenutearoffmanagerbuild"></a><a name="build"></a> CMenuTearOffManager:: Build

```cpp
void Build(
    UINT uiTearOffBarID,
    CString& strText);
```

### <a name="parameters"></a>Parametry

podczas *uiTearOffBarID*<br/>

podczas *strText*<br/>

### <a name="remarks"></a>Uwagi

## <a name="cmenutearoffmanagercmenutearoffmanager"></a><a name="cmenutearoffmanager"></a> CMenuTearOffManager::CMenuTearOffManager

Konstruuje obiekt [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md) .

```
CMenuTearOffManager();
```

### <a name="remarks"></a>Uwagi

W większości przypadków nie należy tworzyć `CMenuTearOffManager` ręcznie. Struktura aplikacji tworzy `CMenuTearOffManager` obiekt podczas wywoływania [CWinAppEx:: EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus).

## <a name="cmenutearoffmanagergetregpath"></a><a name="getregpath"></a> CMenuTearOffManager::GetRegPath

```
LPCTSTR GetRegPath() const;
```

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cmenutearoffmanagerinitialize"></a><a name="initialize"></a> CMenuTearOffManager:: Initialize

Inicjuje obiekt [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md) .

```
BOOL Initialize(
    LPCTSTR lpszRegEntry,
    UINT uiTearOffMenuFirst,
    UINT uiTearOffMenuLast);
```

### <a name="parameters"></a>Parametry

*lpszRegEntry*<br/>
podczas Ciąg, który zawiera ścieżkę wpisu rejestru. Twoje aplikacje przechowują ustawienia dla pasków odrywanych w tym wpisie rejestru.

*uiTearOffMenuFirst*<br/>
podczas Pierwszy identyfikator menu dla menu odrywania.

*uiTearOffMenuLast*<br/>
podczas Ostatni identyfikator menu dla menu odrywania.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Zakres identyfikatorów menu od *uiTearOffMenuFirst* do *uiTearOffMenuLast* musi być ciągłym interwałem. Interwał definiuje liczbę menu odrywających, które mogą być wyświetlane w tym samym czasie w aplikacji.

## <a name="cmenutearoffmanagerisdynamicid"></a><a name="isdynamicid"></a> CMenuTearOffManager::IsDynamicID

```
BOOL IsDynamicID(UINT uiID) const;
```

### <a name="parameters"></a>Parametry

podczas *uiID*<br/>

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cmenutearoffmanagerparse"></a><a name="parse"></a> CMenuTearOffManager::P arse

```
UINT Parse(CString& str);
```

### <a name="parameters"></a>Parametry

podczas *str*<br/>

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cmenutearoffmanagerreset"></a><a name="reset"></a> CMenuTearOffManager:: Reset

```cpp
void Reset(HMENU hmenu);
```

### <a name="parameters"></a>Parametry

podczas *HMENU*<br/>

### <a name="remarks"></a>Uwagi

## <a name="cmenutearoffmanagersetinuse"></a><a name="setinuse"></a> CMenuTearOffManager::SetInUse

```cpp
void SetInUse(
    UINT uiCmdId,
    BOOL bUse = TRUE);
```

### <a name="parameters"></a>Parametry

podczas *uiCmdId*<br/>

podczas *bUse*<br/>

### <a name="remarks"></a>Uwagi

## <a name="cmenutearoffmanagersetuptearoffmenus"></a><a name="setuptearoffmenus"></a> CMenuTearOffManager::SetupTearOffMenus

```cpp
void SetupTearOffMenus(HMENU hMenu);
```

### <a name="parameters"></a>Parametry

podczas *HMENU*<br/>

### <a name="remarks"></a>Uwagi

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CWinAppEx](../../mfc/reference/cwinappex-class.md)

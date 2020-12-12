---
description: 'Dowiedz się więcej na temat: Klasa CSettingsStoreSP'
title: Klasa CSettingsStoreSP
ms.date: 11/04/2016
f1_keywords:
- CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP::CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP::Create
- AFXSETTINGSSTORE/CSettingsStoreSP::SetRuntimeClass
helpviewer_keywords:
- CSettingsStoreSP [MFC], CSettingsStoreSP
- CSettingsStoreSP [MFC], Create
- CSettingsStoreSP [MFC], SetRuntimeClass
ms.assetid: bcd37f40-cfd4-4d17-a5ce-3bfabe995dcc
ms.openlocfilehash: 67e9f881fc43722ab568aa7f149fc7a2b44cc764
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264690"
---
# <a name="csettingsstoresp-class"></a>Klasa CSettingsStoreSP

`CSettingsStoreSP`Klasa jest klasą pomocnika, której można użyć do tworzenia wystąpień [klasy CSettingsStore](../../mfc/reference/csettingsstore-class.md).

## <a name="syntax"></a>Składnia

```
class CSettingsStoreSP
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CSettingsStoreSP::CSettingsStoreSP](#csettingsstoresp)|Konstruuje `CSettingsStoreSP` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CSettingsStoreSP:: Create](#create)|Tworzy wystąpienie klasy, która pochodzi od `CSettingsStore` .|
|[CSettingsStoreSP::SetRuntimeClass](#setruntimeclass)|Ustawia klasę środowiska uruchomieniowego. `Create`Metoda używa klasy środowiska uruchomieniowego w celu określenia klasy obiektów do utworzenia.|

### <a name="data-members"></a>Elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|`m_dwUserData`|Niestandardowe dane użytkownika przechowywane w `CSettingsStoreSP` obiekcie. Te dane są dostarczane w konstruktorze `CSettingsStoreSP` obiektu.|
|`m_pRegistry`|`CSettingsStore`Obiekt pochodny `Create` tworzony przez metodę.|

## <a name="remarks"></a>Uwagi

Można użyć `CSettingsStoreSP` klasy, aby przekierować wszystkie operacje rejestru MFC do innych lokalizacji, takich jak plik XML lub baza danych. W tym celu wykonaj następujące kroki:

1. Utwórz klasę (na przykład `CMyStore` ) i poprowadzi ją od `CSettingsStore` .

1. Użyj [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate) i [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate) makra z klasą niestandardową `CSettingsStore` , aby włączyć tworzenie dynamiczne.

1. Zastąp funkcje wirtualne i zaimplementuj `Read` `Write` funkcje i w klasie niestandardowej. Zaimplementuj inne funkcje, aby odczytywać i zapisywać dane w żądanej lokalizacji.

1. W aplikacji Wywołaj `CSettingsStoreSP::SetRuntimeClass` i przekaż wskaźnik do [struktury CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) uzyskanej z klasy.

Zawsze, gdy platforma zwykle uzyskuje dostęp do rejestru, będzie teraz dynamicznie tworzyć wystąpienie klasy niestandardowej i używać jej do odczytu lub zapisu danych.

`CSettingsStoreSP::SetRuntimeClass` używa globalnej zmiennej statycznej. W związku z tym tylko jeden magazyn niestandardowy jest dostępny w danym momencie.

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxsettingsstore. h

## <a name="csettingsstorespcreate"></a><a name="create"></a> CSettingsStoreSP:: Create

Tworzy nowe wystąpienie obiektu pochodnego od [klasy CSettingsStore](../../mfc/reference/csettingsstore-class.md).

```
CSettingsStore& CSettingsStoreSP Create(
    BOOL bAdmin,
    BOOL bReadOnly);
```

### <a name="parameters"></a>Parametry

*bAdmin*<br/>
podczas Parametr logiczny, który określa, czy `CSettingsStore` obiekt jest tworzony w trybie administratora.

*bReadOnly*<br/>
podczas Parametr logiczny, który określa, czy `CSettingsStore` obiekt jest tworzony dla dostępu tylko do odczytu.

### <a name="return-value"></a>Wartość zwracana

Odwołanie do nowo utworzonego `CSettingsStore` obiektu.

### <a name="remarks"></a>Uwagi

Aby określić typ tworzonego obiektu, można użyć metody [CSettingsStoreSP:: SetRuntimeClass](#setruntimeclass) `CSettingsStoreSP::Create` . Domyślnie ta metoda tworzy `CSettingsStore` obiekt.

Jeśli utworzysz `CSettingsStore` obiekt w trybie administratora, domyślną lokalizacją dla całego dostępu do rejestru jest HKEY_LOCAL_MACHINE. W przeciwnym razie domyślną lokalizacją dla całego dostępu do rejestru jest HKEY_CURRENT_USER.

Jeśli *bAdmin* ma wartość true, aplikacja musi mieć prawa administracyjne. W przeciwnym razie zakończy się niepowodzeniem, gdy próbuje uzyskać dostęp do rejestru.

### <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób użycia `Create` metody `CSettingsStoreSP` klasy.

[!code-cpp[NVC_MFC_RibbonApp#33](../../mfc/reference/codesnippet/cpp/csettingsstoresp-class_1.cpp)]

## <a name="csettingsstorespcsettingsstoresp"></a><a name="csettingsstoresp"></a> CSettingsStoreSP::CSettingsStoreSP

Konstruuje obiekt [klasy CSettingsStoreSP](../../mfc/reference/csettingsstoresp-class.md) .

```
CSettingsStoreSP::CSettingsStoreSP(DWORD dwUserData = 0);
```

### <a name="parameters"></a>Parametry

*dwUserData*<br/>
podczas Dane zdefiniowane przez użytkownika, które `CSettingsStoreSP` są przechowywane w obiektach.

### <a name="remarks"></a>Uwagi

`CSettingsStoreSP`Obiekt przechowuje dane z *dwUserData* w zmiennej chronionej składowej `m_dwUserData` .

## <a name="csettingsstorespsetruntimeclass"></a><a name="setruntimeclass"></a> CSettingsStoreSP::SetRuntimeClass

Ustawia klasę środowiska uruchomieniowego. Metoda [CSettingsStoreSP:: Create](#create) używa klasy środowiska uruchomieniowego w celu określenia typu obiektu do utworzenia.

```
static BOOL __stdcall CSettingsStoreSP::SetRuntimeClass(CRuntimeClass* pRTI);
```

### <a name="parameters"></a>Parametry

*pRTI*<br/>
podczas Wskaźnik do informacji o klasie środowiska uruchomieniowego klasy pochodzącej od [klasy CSettingsStore](../../mfc/reference/csettingsstore-class.md).

### <a name="return-value"></a>Wartość zwracana

Wartość TRUE, jeśli powodzenie; FAŁSZ, jeśli Klasa identyfikowana przez *pRTI* nie pochodzi od klasy `CSettingsStore` .

### <a name="remarks"></a>Uwagi

[Klasy CSettingsStoreSP](../../mfc/reference/csettingsstoresp-class.md) można użyć do wyprowadzania klas z `CSettingsStore` . Użyj metody, `SetRuntimeClass` Jeśli chcesz utworzyć obiekty klasy niestandardowej, która pochodzi od `CSettingsStore` .

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa CSettingsStore](../../mfc/reference/csettingsstore-class.md)

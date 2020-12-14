---
description: 'Dowiedz się więcej na temat: Klasa CDockState'
title: Klasa CDockState
ms.date: 11/04/2016
f1_keywords:
- CDockState
- AFXADV/CDockState
- AFXADV/CDockState::Clear
- AFXADV/CDockState::GetVersion
- AFXADV/CDockState::LoadState
- AFXADV/CDockState::SaveState
- AFXADV/CDockState::m_arrBarInfo
helpviewer_keywords:
- CDockState [MFC], Clear
- CDockState [MFC], GetVersion
- CDockState [MFC], LoadState
- CDockState [MFC], SaveState
- CDockState [MFC], m_arrBarInfo
ms.assetid: 09e7c10b-3abd-4cb2-ad36-42420fe6bc36
ms.openlocfilehash: 4bdc17ec5a09b812609b8aa71e3f361603c1106f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184962"
---
# <a name="cdockstate-class"></a>Klasa CDockState

Serializowana `CObject` Klasa, która ładuje, zwalnia lub czyści stan co najmniej jednego zadokowanego paska sterowania w trwałej pamięci (pliku).

## <a name="syntax"></a>Składnia

```
class CDockState : public CObject
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CDockState:: Clear](#clear)|Czyści informacje o stanie dokowania.|
|[CDockState:: GetVersion](#getversion)|Pobiera numer wersji stanu przechowywanego paska.|
|[CDockState:: LoadState](#loadstate)|Pobiera informacje o stanie z rejestru lub. Plik INI.|
|[CDockState:: SaveState](#savestate)|Zapisuje informacje o stanie w rejestrze lub pliku INI.|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CDockState:: m_arrBarInfo](#m_arrbarinfo)|Tablica wskaźników do przechowywanych informacji o stanie dokowania z jednym wpisem na każdym pasku sterowania.|

## <a name="remarks"></a>Uwagi

Stan dokowania obejmuje rozmiar i położenie paska oraz wskazuje, czy jest zadokowany. Podczas pobierania zapisanego stanu dokowania `CDockState` sprawdza położenie paska i, jeśli pasek nie jest widoczny z bieżącymi ustawieniami ekranu, `CDockState` skaluje położenie paska tak, aby był widoczny. Głównym celem `CDockState` jest przechowywanie całego stanu wielu pasków kontroli oraz umożliwienie zapisania tego stanu i załadowania go do rejestru, aplikacji. Plik INI lub w postaci binarnej jako część `CArchive` zawartości obiektu.

Pasek może być dowolnym było dokowaćm paskiem sterowania, w tym paskiem narzędzi, paskiem stanu lub paskiem okna dialogowego. `CDockState` obiekty są zapisywane i odczytywane z pliku lub z niego za pośrednictwem `CArchive` obiektu.

[Obiektu CFrameWnd:: GetDockState](../../mfc/reference/cframewnd-class.md#getdockstate) pobiera informacje o stanie wszystkich obiektów okna ramki `CControlBar` i umieszcza je w `CDockState` obiekcie. Następnie można napisać zawartość `CDockState` obiektu do magazynu przy użyciu [serializacji](../../mfc/reference/cobject-class.md#serialize) lub [CDockState:: SaveState](#savestate). Jeśli później chcesz przywrócić stan pasków sterowania w oknie ramka, możesz załadować stan z `Serialize` lub [CDockState:: LoadState](#loadstate), a następnie użyć [obiektu CFrameWnd:: SetDockState](../../mfc/reference/cframewnd-class.md#setdockstate) , aby zastosować zapisany stan do pasków sterowania okna ramki.

Aby uzyskać więcej informacji na temat dokowania pasków sterowania, zobacz artykuły [paski sterowania](../../mfc/control-bars.md), [paski narzędzi: dokowanie i przestawne](../../mfc/docking-and-floating-toolbars.md)oraz [okna ramowe](../../mfc/frame-windows.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

`CDockState`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxadv. h

## <a name="cdockstateclear"></a><a name="clear"></a> CDockState:: Clear

Wywołaj tę funkcję, aby wyczyścić wszystkie informacje dotyczące dokowania przechowywane w `CDockState` obiekcie.

```cpp
void Clear();
```

### <a name="remarks"></a>Uwagi

Dotyczy to nie tylko tego, czy pasek jest zadokowany, ale rozmiar i położenie paska oraz czy jest on widoczny.

## <a name="cdockstategetversion"></a><a name="getversion"></a> CDockState:: GetVersion

Wywołaj tę funkcję, aby pobrać numer wersji stanu przechowywanego paska.

```
DWORD GetVersion();
```

### <a name="return-value"></a>Wartość zwracana

1, jeśli przechowywane informacje o pasku są starsze niż bieżący stan paska; 2 Jeśli przechowywane informacje o pasku są takie same jak bieżący stan paska.

### <a name="remarks"></a>Uwagi

Obsługa wersji umożliwia skorygowany pasek w celu dodania nowych trwałych właściwości i nadal może wykrywać i ładować stan trwały utworzony przez wcześniejszą wersję paska.

## <a name="cdockstateloadstate"></a><a name="loadstate"></a> CDockState:: LoadState

Wywołaj tę funkcję, aby pobrać informacje o stanie z rejestru lub. Plik INI.

```cpp
void LoadState(LPCTSTR lpszProfileName);
```

### <a name="parameters"></a>Parametry

*lpszProfileName*<br/>
Wskazuje na ciąg o wartości null-teminated, który określa nazwę sekcji w pliku inicjującym lub klucz w rejestrze systemu Windows, w którym są przechowywane informacje o stanie.

### <a name="remarks"></a>Uwagi

Nazwa profilu jest częścią aplikacji. Plik INI lub rejestr zawierający informacje o stanie pasków. Informacje o stanie paska sterowania można zapisać w rejestrze lub. Plik INI z `SaveState` .

## <a name="cdockstatem_arrbarinfo"></a><a name="m_arrbarinfo"></a> CDockState:: m_arrBarInfo

`CPtrArray`Obiekt, który jest tablicą wskaźników do przechowywanych informacji paska sterowania dla każdego paska sterowania, który ma zapisane informacje o stanie w `CDockState` obiekcie.

```
CPtrArray m_arrBarInfo;
```

## <a name="cdockstatesavestate"></a><a name="savestate"></a> CDockState:: SaveState

Wywołaj tę funkcję, aby zapisać informacje o stanie w rejestrze lub. Plik INI.

```cpp
void SaveState(LPCTSTR lpszProfileName);
```

### <a name="parameters"></a>Parametry

*lpszProfileName*<br/>
Wskazuje na ciąg o wartości null-teminated, który określa nazwę sekcji w pliku inicjującym lub klucz w rejestrze systemu Windows, w którym są przechowywane informacje o stanie.

### <a name="remarks"></a>Uwagi

Nazwa profilu jest częścią aplikacji. Plik INI lub rejestr zawierający informacje o stanie paska sterowania. `SaveState` powoduje także zapisanie bieżącego rozmiaru ekranu. Możesz pobrać informacje o pasku sterowania z rejestru lub. Plik INI z `LoadState` .

## <a name="see-also"></a>Zobacz też

[Klasa CObject](../../mfc/reference/cobject-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)

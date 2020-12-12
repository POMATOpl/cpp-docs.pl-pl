---
description: 'Dowiedz się więcej na temat: Klasa CDataPathProperty'
title: Klasa CDataPathProperty
ms.date: 11/04/2016
f1_keywords:
- CDataPathProperty
- AFXCTL/CDataPathProperty
- AFXCTL/CDataPathProperty::CDataPathProperty
- AFXCTL/CDataPathProperty::GetControl
- AFXCTL/CDataPathProperty::GetPath
- AFXCTL/CDataPathProperty::Open
- AFXCTL/CDataPathProperty::ResetData
- AFXCTL/CDataPathProperty::SetControl
- AFXCTL/CDataPathProperty::SetPath
helpviewer_keywords:
- CDataPathProperty [MFC], CDataPathProperty
- CDataPathProperty [MFC], GetControl
- CDataPathProperty [MFC], GetPath
- CDataPathProperty [MFC], Open
- CDataPathProperty [MFC], ResetData
- CDataPathProperty [MFC], SetControl
- CDataPathProperty [MFC], SetPath
ms.assetid: 1f96efdb-54e4-460b-862c-eba5d4103488
ms.openlocfilehash: 7d9ff9f380fd44d5261374879bab63c9925c4442
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247959"
---
# <a name="cdatapathproperty-class"></a>Klasa CDataPathProperty

Implementuje właściwość kontrolki OLE, która może zostać załadowana asynchronicznie.

## <a name="syntax"></a>Składnia

```
class CDataPathProperty : public CAsyncMonikerFile
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CDataPathProperty::CDataPathProperty](#cdatapathproperty)|Konstruuje `CDataPathProperty` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CDataPathProperty:: GetControl](#getcontrol)|Pobiera asynchroniczną kontrolkę OLE skojarzoną z `CDataPathProperty` obiektem.|
|[CDataPathProperty:: GetPath](#getpath)|Pobiera nazwę ścieżki właściwości.|
|[CDataPathProperty:: Open](#open)|Inicjuje ładowanie właściwości asynchronicznej skojarzonej kontrolki ActiveX (OLE).|
|[CDataPathProperty:: ResetData](#resetdata)|Wywołania `CAsyncMonikerFile::OnDataAvailable` do powiadamiania kontenera o zmianach właściwości kontrolki.|
|[CDataPathProperty:: SetControl](#setcontrol)|Ustawia asynchroniczną kontrolkę ActiveX (OLE) skojarzoną z właściwością.|
|[CDataPathProperty:: SetPath](#setpath)|Ustawia nazwę ścieżki właściwości.|

## <a name="remarks"></a>Uwagi

Właściwości asynchroniczne są ładowane po asynchronicznym inicjacji.

Klasa `CDataPathProperty` pochodzi od `CAysncMonikerFile` . Aby zaimplementować właściwości asynchroniczne w kontrolkach OLE, należy utworzyć klasę z `CDataPathProperty` i zastąpić [OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable).

Aby uzyskać więcej informacji o sposobach korzystania z monikerów asynchronicznych i kontrolek ActiveX w aplikacjach internetowych, zobacz następujące artykuły:

- [Internet — pierwsze kroki: kontrolki ActiveX](../../mfc/activex-controls-on-the-internet.md)

- [Pierwsze kroki w Internecie: monikery asynchroniczne](../../mfc/asynchronous-monikers-on-the-internet.md)

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

[CMonikerFile](../../mfc/reference/cmonikerfile-class.md)

[CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)

`CDataPathProperty`

## <a name="requirements"></a>Wymagania

**Nagłówek:** 'afxctl. h

## <a name="cdatapathpropertycdatapathproperty"></a><a name="cdatapathproperty"></a> CDataPathProperty::CDataPathProperty

Konstruuje `CDataPathProperty` obiekt.

```
CDataPathProperty(COleControl* pControl = NULL);
CDataPathProperty(LPCTSTR lpszPath, COleControl* pControl = NULL);
```

### <a name="parameters"></a>Parametry

*pControl*<br/>
Wskaźnik do obiektu formantu OLE, który ma zostać skojarzony z tym `CDataPathProperty` obiektem.

*lpszPath*<br/>
Ścieżka, która może być bezwzględna lub względna, użyta do utworzenia asynchronicznej monikera, która odwołuje się do rzeczywistej absolutnej lokalizacji właściwości. `CDataPathProperty` używa adresów URL, a nie nazw plików. Jeśli chcesz, aby `CDataPathProperty` obiekt dla pliku, poprzedź `file://` ścieżkę.

### <a name="remarks"></a>Uwagi

`COleControl`Obiekt wskazywany przez *pControl* jest używany przez `Open` i pobierany przez klasy pochodne. Jeśli *pControl* ma wartość null, formant używany z elementem `Open` powinien być ustawiony przy użyciu `SetControl` . Jeśli *lpszPath* ma wartość null, można przekazać ścieżkę przez `Open` lub ustawić ją z `SetPath` .

## <a name="cdatapathpropertygetcontrol"></a><a name="getcontrol"></a> CDataPathProperty:: GetControl

Wywołaj tę funkcję elementu członkowskiego, aby pobrać `COleControl` obiekt skojarzony z `CDataPathProperty` obiektem.

```
COleControl* GetControl();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca wskaźnik do kontrolki OLE skojarzonej z `CDataPathProperty` obiektem. Wartość NULL, jeśli nie jest skojarzona żadna kontrola.

## <a name="cdatapathpropertygetpath"></a><a name="getpath"></a> CDataPathProperty:: GetPath

Wywołaj tę funkcję elementu członkowskiego, aby pobrać ścieżkę, ustawić, kiedy `CDataPathProperty` obiekt został skonstruowany lub określony w `Open` lub określony w poprzednim wywołaniu `SetPath` funkcji składowej.

```
CString GetPath() const;
```

### <a name="return-value"></a>Wartość zwracana

Zwraca nazwę ścieżki do samej właściwości. Może być puste, jeśli nie określono ścieżki.

## <a name="cdatapathpropertyopen"></a><a name="open"></a> CDataPathProperty:: Open

Wywołaj tę funkcję elementu członkowskiego, aby zainicjować ładowanie właściwości asynchronicznej skojarzonej kontrolki.

```
virtual BOOL Open(
    COleControl* pControl,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszPath,
    COleControl* pControl,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszPath,
    CFileException* pError = NULL);

virtual BOOL Open(CFileException* pError = NULL);
```

### <a name="parameters"></a>Parametry

*pControl*<br/>
Wskaźnik do obiektu formantu OLE, który ma zostać skojarzony z tym `CDataPathProperty` obiektem.

*pError*<br/>
Wskaźnik do wyjątku pliku. W przypadku błędu, zostanie ustawiony na przyczynę.

*lpszPath*<br/>
Ścieżka, która może być bezwzględna lub względna, użyta do utworzenia asynchronicznej monikera, która odwołuje się do rzeczywistej absolutnej lokalizacji właściwości. `CDataPathProperty` używa adresów URL, a nie nazw plików. Jeśli chcesz, aby `CDataPathProperty` obiekt dla pliku, poprzedź `file://` ścieżkę.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Funkcja próbuje uzyskać `IBindHost` interfejs z formantu.

Przed wywołaniem `Open` bez ścieżki należy ustawić wartość ścieżki właściwości. Można to zrobić, gdy obiekt jest konstruowany lub wywołując `SetPath` funkcję członkowską.

Przed wywołaniem `Open` bez formantu Kontrolka ActiveX (wcześniej znana jako kontrolka OLE) może być skojarzona z obiektem. Można to zrobić, gdy obiekt jest konstruowany lub wywołując `SetControl` .

Wszystkie przeciążenia elementu [CAsyncMonikerFile:: Open](../../mfc/reference/casyncmonikerfile-class.md#open) są również dostępne z programu `CDataPathProperty` .

## <a name="cdatapathpropertyresetdata"></a><a name="resetdata"></a> CDataPathProperty:: ResetData

Wywołaj tę funkcję, aby otrzymać `CAsyncMonikerFile::OnDataAvailable` powiadomienie kontenera o zmianach właściwości kontrolki, a wszystkie informacje ładowane asynchronicznie nie są już użyteczne.

```
virtual void ResetData();
```

### <a name="remarks"></a>Uwagi

Otwieranie należy uruchomić ponownie. Klasy pochodne mogą przesłaniać tę funkcję dla różnych wartości domyślnych.

## <a name="cdatapathpropertysetcontrol"></a><a name="setcontrol"></a> CDataPathProperty:: SetControl

Wywołaj tę funkcję elementu członkowskiego, aby skojarzyć asynchroniczny formant OLE z `CDataPathProperty` obiektem.

```cpp
void SetControl(COleControl* pControl);
```

### <a name="parameters"></a>Parametry

*pControl*<br/>
Wskaźnik do asynchronicznej kontrolki OLE, która ma być skojarzona z właściwością.

## <a name="cdatapathpropertysetpath"></a><a name="setpath"></a> CDataPathProperty:: SetPath

Wywołaj tę funkcję elementu członkowskiego, aby ustawić nazwę ścieżki właściwości.

```cpp
void SetPath(LPCTSTR lpszPath);
```

### <a name="parameters"></a>Parametry

*lpszPath*<br/>
Ścieżka, która może być bezwzględna lub względna, do właściwości, która jest ładowana asynchronicznie. `CDataPathProperty` używa adresów URL, a nie nazw plików. Jeśli chcesz, aby `CDataPathProperty` obiekt dla pliku, poprzedź `file://` ścieżkę.

## <a name="see-also"></a>Zobacz też

[Przykład obrazu MFC](../../overview/visual-cpp-samples.md)<br/>
[Klasa CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)

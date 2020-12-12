---
description: 'Dowiedz się więcej na temat: Klasa CCachedDataPathProperty'
title: Klasa CCachedDataPathProperty
ms.date: 11/04/2016
f1_keywords:
- CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty::CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty::m_Cache
helpviewer_keywords:
- CCachedDataPathProperty [MFC], CCachedDataPathProperty
- CCachedDataPathProperty [MFC], m_Cache
ms.assetid: 0d81356b-4fe5-43f6-aed2-2eb5a5485706
ms.openlocfilehash: a61d2553afc4415da29399293843deb1be5f113d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122502"
---
# <a name="ccacheddatapathproperty-class"></a>Klasa CCachedDataPathProperty

Implementuje właściwość kontrolki OLE przetransferowaną asynchronicznie i buforowaną w pliku pamięci.

## <a name="syntax"></a>Składnia

```
class CCachedDataPathProperty : public CDataPathProperty
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CCachedDataPathProperty::CCachedDataPathProperty](#ccacheddatapathproperty)|Konstruuje `CCachedDataPathProperty` obiekt.|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CCachedDataPathProperty:: m_Cache](#m_cache)|`CMemFile` Obiekt, w którym mają być buforowane dane.|

## <a name="remarks"></a>Uwagi

Plik pamięci jest przechowywany w pamięci RAM, a nie na dysku i jest przydatny do szybkich transferów tymczasowych.

Wraz z `CAysncMonikerFile` programem `CDataPathProperty` i `CCachedDataPathProperty` oferuje funkcje używania monikerów asynchronicznych w kontrolkach OLE. `CCachedDataPathProperty`Obiekty umożliwiają transfer danych asynchronicznie z adresu URL lub źródła pliku i przechowywanie ich w pliku pamięci za pośrednictwem `m_Cache` zmiennej publicznej. Wszystkie dane są przechowywane w pliku pamięci i nie ma potrzeby przesłonięcia [OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable) , chyba że chcesz oglądać powiadomienia i reagować. Na przykład, jeśli przesyłasz duże. Plik GIF i chcesz powiadomić swój formant o dostarczeniu większej ilości danych, który powinien zostać ponownie narysowany, Przesłoń, `OnDataAvailable` Aby zgłosić powiadomienie.

Klasa `CCachedDataPathProperty` pochodzi od `CDataPathProperty` .

Więcej informacji o sposobach korzystania z monikerów asynchronicznych i kontrolek ActiveX w aplikacjach internetowych znajduje się w następujących tematach:

- [Internet — pierwsze kroki: kontrolki ActiveX](../../mfc/activex-controls-on-the-internet.md)

- [Pierwsze kroki w Internecie: monikery asynchroniczne](../../mfc/asynchronous-monikers-on-the-internet.md)

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

[CMonikerFile](../../mfc/reference/cmonikerfile-class.md)

[CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)

[CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)

`CCachedDataPathProperty`

## <a name="requirements"></a>Wymagania

**Nagłówek:** 'afxctl. h

## <a name="ccacheddatapathpropertyccacheddatapathproperty"></a><a name="ccacheddatapathproperty"></a> CCachedDataPathProperty::CCachedDataPathProperty

Konstruuje `CCachedDataPathProperty` obiekt.

```
CCachedDataPathProperty(COleControl* pControl = NULL);

CCachedDataPathProperty(
    LPCTSTR lpszPath,
    COleControl* pControl = NULL);
```

### <a name="parameters"></a>Parametry

*pControl*<br/>
Wskaźnik do obiektu kontrolki ActiveX, który ma zostać skojarzony z tym `CCachedDataPathProperty` obiektem.

*lpszPath*<br/>
Ścieżka, która może być bezwzględna lub względna, użyta do utworzenia asynchronicznej monikera, która odwołuje się do rzeczywistej absolutnej lokalizacji właściwości. `CCachedDataPathProperty` używa adresów URL, a nie nazw plików. Jeśli chcesz, aby `CCachedDataPathProperty` obiekt dla pliku, poprzedź File://do ścieżki.

### <a name="remarks"></a>Uwagi

`COleControl`Obiekt wskazywany przez *pControl* jest używany przez [otwieranie](../../mfc/reference/cdatapathproperty-class.md#open) i pobieranie przez klasy pochodne. Jeśli *pControl* ma wartość null, formant używany z elementem `Open` powinien być ustawiony za pomocą [SetControl](../../mfc/reference/cdatapathproperty-class.md#setcontrol). Jeśli *lpszPath* ma wartość null, można przekazać ścieżkę przez `Open` lub ustawić ją przy użyciu [SetPath](../../mfc/reference/cdatapathproperty-class.md#setpath).

## <a name="ccacheddatapathpropertym_cache"></a><a name="m_cache"></a> CCachedDataPathProperty:: m_Cache

Zawiera nazwę klasy pliku pamięci, w której znajdują się dane przechowywane w pamięci podręcznej.

```
CMemFile m_Cache;
```

### <a name="remarks"></a>Uwagi

Plik pamięci jest przechowywany w pamięci RAM, a nie na dysku.

## <a name="see-also"></a>Zobacz też

[Klasa CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)

---
description: 'Dowiedz się więcej na temat: Klasa COleLinkingDoc'
title: Klasa COleLinkingDoc
ms.date: 11/04/2016
f1_keywords:
- COleLinkingDoc
- AFXOLE/COleLinkingDoc
- AFXOLE/COleLinkingDoc::COleLinkingDoc
- AFXOLE/COleLinkingDoc::Register
- AFXOLE/COleLinkingDoc::Revoke
- AFXOLE/COleLinkingDoc::OnFindEmbeddedItem
- AFXOLE/COleLinkingDoc::OnGetLinkedItem
helpviewer_keywords:
- COleLinkingDoc [MFC], COleLinkingDoc
- COleLinkingDoc [MFC], Register
- COleLinkingDoc [MFC], Revoke
- COleLinkingDoc [MFC], OnFindEmbeddedItem
- COleLinkingDoc [MFC], OnGetLinkedItem
ms.assetid: 9f547f35-2f95-427f-b9c0-85c31940198b
ms.openlocfilehash: 10cf9bb81c4cbbd324b95a13dc2fa44548266583
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226912"
---
# <a name="colelinkingdoc-class"></a>Klasa COleLinkingDoc

Klasa bazowa dla dokumentów kontenera OLE, które obsługują łączenie z osadzonymi elementami.

## <a name="syntax"></a>Składnia

```
class COleLinkingDoc : public COleDocument
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[COleLinkingDoc::COleLinkingDoc](#colelinkingdoc)|Konstruuje `COleLinkingDoc` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[COleLinkingDoc:: register](#register)|Rejestruje dokument przy użyciu bibliotek DLL systemu OLE.|
|[COleLinkingDoc:: odwołaj](#revoke)|Odwołuje rejestrację dokumentu.|

### <a name="protected-methods"></a>Metody chronione

|Nazwa|Opis|
|----------|-----------------|
|[COleLinkingDoc::OnFindEmbeddedItem](#onfindembeddeditem)|Znajduje określony element osadzony.|
|[COleLinkingDoc::OnGetLinkedItem](#ongetlinkeditem)|Znajduje określony połączony element.|

## <a name="remarks"></a>Uwagi

Aplikacja kontenera obsługująca łączenie z elementami osadzonymi jest nazywana "kontenerem łącza". Przykładowa aplikacja [OCLIENT](../../overview/visual-cpp-samples.md) to przykładowy kontener łącza.

Gdy źródło połączonego elementu jest elementem osadzonym w innym dokumencie zawierającym dokument musi być załadowany, aby można było edytować element osadzony. Z tego powodu kontener łącza musi być w stanie uruchomić przez inną aplikację kontenera, gdy użytkownik chce edytować źródło połączonego elementu. Aplikacja musi również używać klasy [element COleTemplateServer](../../mfc/reference/coletemplateserver-class.md) , aby można było tworzyć dokumenty po uruchomieniu programowo.

Aby kontener łączy kontener, należy utworzyć klasę dokumentu od `COleLinkingDoc` zamiast [COleDocument](../../mfc/reference/coledocument-class.md). Podobnie jak w przypadku każdego innego kontenera OLE, należy zaprojektować klasę do przechowywania danych natywnych aplikacji, a także elementów osadzonych lub połączonych. Ponadto należy projektować struktury danych do przechowywania danych natywnych. W przypadku zdefiniowania `CDocItem` klasy pochodnej dla danych natywnych aplikacji można użyć interfejsu zdefiniowanego przez program `COleDocument` do przechowywania danych natywnych oraz danych OLE.

Aby umożliwić uruchamianie aplikacji programowo przez inny kontener, należy zadeklarować `COleTemplateServer` obiekt jako element członkowski `CWinApp` klasy pochodnej aplikacji:

[!code-cpp[NVC_MFCOleContainer#23](../../mfc/codesnippet/cpp/colelinkingdoc-class_1.h)]

W `InitInstance` funkcji członkowskiej `CWinApp` klasy pochodnej Utwórz szablon dokumentu i określ `COleLinkingDoc` klasę pochodną jako klasę dokumentu:

[!code-cpp[NVC_MFCOleContainer#24](../../mfc/codesnippet/cpp/colelinkingdoc-class_2.cpp)]

Połącz `COleTemplateServer` obiekt z szablonami dokumentów `ConnectTemplate` , wywołując funkcję członkowską obiektu i rejestrując wszystkie obiekty klasy w systemie OLE, wywołując `COleTemplateServer::RegisterAll` :

[!code-cpp[NVC_MFCOleContainer#25](../../mfc/codesnippet/cpp/colelinkingdoc-class_3.cpp)]

Aby zapoznać się z przykładową `CWinApp` definicją i funkcją klasy pochodnej `InitInstance` , zobacz OCLIENT. H i OCLIENT. CPP w przykładowej [OCLIENT](../../overview/visual-cpp-samples.md)MFC.

Aby uzyskać więcej informacji na temat korzystania z programu `COleLinkingDoc` , zobacz [kontenery artykułów: implementowanie kontenera](../../mfc/containers-implementing-a-container.md) i [kontenerów: funkcje zaawansowane](../../mfc/containers-advanced-features.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

[COleDocument](../../mfc/reference/coledocument-class.md)

`COleLinkingDoc`

## <a name="requirements"></a>Wymagania

**Nagłówek:** Afxole. h

## <a name="colelinkingdoccolelinkingdoc"></a><a name="colelinkingdoc"></a> COleLinkingDoc::COleLinkingDoc

Konstruuje `COleLinkingDoc` obiekt bez rozpoczynania komunikacji z bibliotekami DLL systemu OLE.

```
COleLinkingDoc();
```

### <a name="remarks"></a>Uwagi

Musisz wywołać `Register` funkcję członkowską, aby poinformować OLE, że dokument jest otwarty.

## <a name="colelinkingdoconfindembeddeditem"></a><a name="onfindembeddeditem"></a> COleLinkingDoc::OnFindEmbeddedItem

Wywoływane przez platformę, aby określić, czy dokument zawiera osadzony element OLE o określonej nazwie.

```
virtual COleClientItem* OnFindEmbeddedItem(LPCTSTR lpszItemName);
```

### <a name="parameters"></a>Parametry

*lpszItemName*<br/>
Wskaźnik na nazwę zażądanego osadzonego elementu OLE.

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do określonego elementu; Wartość NULL, jeśli nie można odnaleźć elementu.

### <a name="remarks"></a>Uwagi

Domyślna implementacja przeszukuje listę elementów osadzonych dla elementu o określonej nazwie (w porównaniu z rozróżnianą wielkością liter). Zastąp tę funkcję, jeśli masz własną metodę przechowywania lub nazywania osadzonych elementów OLE.

## <a name="colelinkingdocongetlinkeditem"></a><a name="ongetlinkeditem"></a> COleLinkingDoc::OnGetLinkedItem

Wywoływane przez platformę, aby sprawdzić, czy dokument zawiera połączony element serwera o określonej nazwie.

```
virtual COleServerItem* OnGetLinkedItem(LPCTSTR lpszItemName);
```

### <a name="parameters"></a>Parametry

*lpszItemName*<br/>
Zażądano wskaźnika na nazwę połączonego elementu OLE.

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do określonego elementu; Wartość NULL, jeśli nie można odnaleźć elementu.

### <a name="remarks"></a>Uwagi

Domyślna `COleLinkingDoc` implementacja zawsze zwraca wartość null. Ta funkcja jest przesłonięta w klasie pochodnej, `COleServerDoc` Aby przeszukać listę elementów serwera OLE dla połączonego elementu o określonej nazwie (w przypadku porównania nazw jest uwzględniana wielkość liter). Zastąp tę funkcję, jeśli wdrożono własną metodę przechowywania lub pobierania połączonych elementów serwera.

## <a name="colelinkingdocregister"></a><a name="register"></a> COleLinkingDoc:: register

Informuje biblioteki DLL systemu OLE, że dokument jest otwarty.

```
BOOL Register(
    COleObjectFactory* pFactory,
    LPCTSTR lpszPathName);
```

### <a name="parameters"></a>Parametry

*pFactory*<br/>
Wskaźnik do obiektu fabryki OLE (może mieć wartość NULL).

*lpszPathName*<br/>
Wskaźnik do w pełni kwalifikowanej ścieżki dokumentu kontenera.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli dokument został pomyślnie zarejestrowany; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Wywołaj tę funkcję podczas tworzenia lub otwierania pliku o nazwie w celu zarejestrowania dokumentu przy użyciu bibliotek DLL systemu OLE. Nie ma potrzeby wywoływania tej funkcji, jeśli dokument reprezentuje element osadzony.

Jeśli używasz `COleTemplateServer` w aplikacji, `Register` jest on wywoływany przez `COleLinkingDoc` implementację `OnNewDocument` , `OnOpenDocument` i `OnSaveDocument` .

## <a name="colelinkingdocrevoke"></a><a name="revoke"></a> COleLinkingDoc:: odwołaj

Informuje o bibliotekach DLL systemu OLE, że dokument nie jest już otwarty.

```cpp
void Revoke();
```

### <a name="remarks"></a>Uwagi

Wywołaj tę funkcję, aby odwołać rejestrację dokumentu w bibliotekach DLL systemu OLE.

Należy wywołać tę funkcję podczas zamykania nazwanego pliku, ale zazwyczaj nie trzeba go wywoływać bezpośrednio. `Revoke` jest wywoływana dla użytkownika przez `COleLinkingDoc` implementację `OnCloseDocument` , `OnNewDocument` , `OnOpenDocument` i `OnSaveDocument` .

## <a name="see-also"></a>Zobacz też

[Przykład OCLIENT MFC](../../overview/visual-cpp-samples.md)<br/>
[Klasa COleDocument](../../mfc/reference/coledocument-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa CDocTemplate](../../mfc/reference/cdoctemplate-class.md)

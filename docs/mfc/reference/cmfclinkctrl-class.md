---
description: 'Dowiedz się więcej na temat: Klasa CMFCLinkCtrl'
title: Klasa CMFCLinkCtrl
ms.date: 11/04/2016
f1_keywords:
- CMFCLinkCtrl
- AFXLINKCTRL/CMFCLinkCtrl
- AFXLINKCTRL/CMFCLinkCtrl::SetURL
- AFXLINKCTRL/CMFCLinkCtrl::SetURLPrefix
- AFXLINKCTRL/CMFCLinkCtrl::SizeToContent
- AFXLINKCTRL/CMFCLinkCtrl::OnDrawFocusRect
helpviewer_keywords:
- CMFCLinkCtrl [MFC], SetURL
- CMFCLinkCtrl [MFC], SetURLPrefix
- CMFCLinkCtrl [MFC], SizeToContent
- CMFCLinkCtrl [MFC], OnDrawFocusRect
ms.assetid: 80f3874d-7cc8-410e-9ff1-62a225f5034b
ms.openlocfilehash: 6951f086ac99c4b8a8260a79ee08d54476694350
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265223"
---
# <a name="cmfclinkctrl-class"></a>Klasa CMFCLinkCtrl

`CMFCLinkCtrl`Klasa wyświetla przycisk jako hiperłącze i wywołuje obiekt docelowy linku po kliknięciu przycisku.

## <a name="syntax"></a>Składnia

```
class CMFCLinkCtrl : public CMFCButton
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCLinkCtrl:: SetURL](#seturl)|Wyświetla określony adres URL jako tekst przycisku.|
|[CMFCLinkCtrl::SetURLPrefix](#seturlprefix)|Ustawia niejawny protokół (na przykład "http:") adresu URL.|
|[CMFCLinkCtrl::SizeToContent](#sizetocontent)|Zmienia rozmiar przycisku, aby zawierał tekst lub mapę bitową przycisku.|

### <a name="protected-methods"></a>Metody chronione

|Nazwa|Opis|
|----------|-----------------|
|[CMFCLinkCtrl::OnDrawFocusRect](#ondrawfocusrect)|Wywoływane przez platformę przed narysowaniem prostokąta fokusu przycisku.|

## <a name="remarks"></a>Uwagi

Po kliknięciu przycisku, który jest pochodną `CMFCLinkCtrl` klasy, struktura przekazuje adres URL przycisku jako parametr do `ShellExecute` metody. Następnie `ShellExecute` Metoda otwiera obiekt docelowy adresu URL.

## <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób ustawiania rozmiaru `CMFCLinkCtrl` obiektu oraz ustawiania adresu URL i etykietki narzędzia w `CMFCLinkCtrl` obiekcie. Ten przykład jest częścią [nowych kontrolek](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#9](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#10](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCButton](../../mfc/reference/cmfcbutton-class.md)

[CMFCLinkCtrl](../../mfc/reference/cmfclinkctrl-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxlinkctrl. h

## <a name="cmfclinkctrlondrawfocusrect"></a><a name="ondrawfocusrect"></a> CMFCLinkCtrl::OnDrawFocusRect

Wywoływane przez platformę przed narysowaniem prostokąta fokusu przycisku.

```
virtual void OnDrawFocusRect(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>Parametry

*Domeny*<br/>
podczas Wskaźnik do kontekstu urządzenia.

*rectClient*<br/>
podczas Prostokąt, który jest powiązany z kontrolką łącza.

### <a name="remarks"></a>Uwagi

Zastąp tę metodę, jeśli chcesz użyć własnego kodu do rysowania prostokąta fokus przycisku.

## <a name="cmfclinkctrlseturl"></a><a name="seturl"></a> CMFCLinkCtrl:: SetURL

Wyświetla określony adres URL jako tekst przycisku.

```cpp
void SetURL(LPCTSTR lpszURL);
```

### <a name="parameters"></a>Parametry

*lpszURL*<br/>
podczas Tekst przycisku do wyświetlenia.

### <a name="remarks"></a>Uwagi

## <a name="cmfclinkctrlseturlprefix"></a><a name="seturlprefix"></a> CMFCLinkCtrl::SetURLPrefix

Ustawia niejawny protokół (na przykład "http:") adresu URL.

```cpp
void SetURLPrefix(LPCTSTR lpszPrefix);
```

### <a name="parameters"></a>Parametry

*lpszPrefix*<br/>
podczas Prefiks protokołu adresu URL.

### <a name="remarks"></a>Uwagi

Użyj tej metody, aby ustawić prefiks adresu URL. Prefiks nie jest wyświetlany na głowie przycisku, ale można go użyć, aby przejść do docelowego adresu URL.

## <a name="cmfclinkctrlsizetocontent"></a><a name="sizetocontent"></a> CMFCLinkCtrl::SizeToContent

Zmienia rozmiar przycisku, aby zawierał tekst lub mapę bitową przycisku.

```
virtual CSize SizeToContent(
    BOOL bVCenter=FALSE,
    BOOL bHCenter=FALSE);
```

### <a name="parameters"></a>Parametry

*bVCenter*<br/>
podczas TRUE, aby wyśrodkować tekst przycisku i mapę bitową w pionie między górną i dolną krawędzią kontrolki linku; w przeciwnym razie FALSE. Wartość domyślna to FALSE.

*bHCenter*<br/>
podczas Wartość TRUE, aby wyśrodkować tekst przycisku i mapę bitową w poziomie między lewą i prawą krawędzią kontrolki link. w przeciwnym razie FALSE. Wartość domyślna to FALSE.

### <a name="return-value"></a>Wartość zwracana

Obiekt [CSize](../../atl-mfc-shared/reference/csize-class.md) , który zawiera nowy rozmiar kontrolki łącza.

### <a name="remarks"></a>Uwagi

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CLinkCtrl](../../mfc/reference/clinkctrl-class.md)<br/>
[Klasa CMFCButton](../../mfc/reference/cmfcbutton-class.md)

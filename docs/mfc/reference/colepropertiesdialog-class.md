---
description: 'Dowiedz się więcej na temat: Klasa COlePropertiesDialog'
title: Klasa COlePropertiesDialog
ms.date: 11/04/2016
f1_keywords:
- COlePropertiesDialog
- AFXODLGS/COlePropertiesDialog
- AFXODLGS/COlePropertiesDialog::COlePropertiesDialog
- AFXODLGS/COlePropertiesDialog::DoModal
- AFXODLGS/COlePropertiesDialog::OnApplyScale
- AFXODLGS/COlePropertiesDialog::m_gp
- AFXODLGS/COlePropertiesDialog::m_lp
- AFXODLGS/COlePropertiesDialog::m_op
- AFXODLGS/COlePropertiesDialog::m_psh
- AFXODLGS/COlePropertiesDialog::m_vp
helpviewer_keywords:
- COlePropertiesDialog [MFC], COlePropertiesDialog
- COlePropertiesDialog [MFC], DoModal
- COlePropertiesDialog [MFC], OnApplyScale
- COlePropertiesDialog [MFC], m_gp
- COlePropertiesDialog [MFC], m_lp
- COlePropertiesDialog [MFC], m_op
- COlePropertiesDialog [MFC], m_psh
- COlePropertiesDialog [MFC], m_vp
ms.assetid: a54dbc89-1447-4329-bd01-00e98ec9e935
ms.openlocfilehash: f0c102412f422ff0eabc9f1ff8e19901845905e8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226769"
---
# <a name="colepropertiesdialog-class"></a>Klasa COlePropertiesDialog

Hermetyzuje wspólne okno dialogowe właściwości obiektu OLE systemu Windows.

## <a name="syntax"></a>Składnia

```
class COlePropertiesDialog : public COleDialog
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[COlePropertiesDialog::COlePropertiesDialog](#colepropertiesdialog)|Konstruuje `COlePropertiesDialog` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[COlePropertiesDialog::D oModal](#domodal)|Wyświetla okno dialogowe i umożliwia użytkownikowi wybranie.|
|[COlePropertiesDialog::OnApplyScale](#onapplyscale)|Wywoływane przez platformę, gdy zmieniono skalę elementu dokumentu.|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[COlePropertiesDialog:: m_gp](#m_gp)|Struktura używana do inicjowania strony "ogólne" `COlePropertiesDialog` obiektu.|
|[COlePropertiesDialog:: m_lp](#m_lp)|Struktura używana do inicjowania strony "link" `COlePropertiesDialog` obiektu.|
|[COlePropertiesDialog:: m_op](#m_op)|Struktura używana do inicjowania `COlePropertiesDialog` obiektu.|
|[COlePropertiesDialog:: m_psh](#m_psh)|Struktura używana do dodawania dodatkowych stron właściwości niestandardowych.|
|[COlePropertiesDialog:: m_vp](#m_vp)|Struktura używana do dostosowywania strony "widok" `COlePropertiesDialog` obiektu.|

## <a name="remarks"></a>Uwagi

Okna dialogowe właściwości wspólnych obiektów OLE zapewniają łatwy sposób wyświetlania i modyfikowania właściwości elementu dokumentu OLE w sposób zgodny ze standardami systemu Windows. Te właściwości obejmują między innymi informacje o pliku reprezentowane przez element dokumentu, opcje wyświetlania ikony i skalowania obrazu oraz informacje o linku elementu (Jeśli element jest połączony).

Aby użyć `COlePropertiesDialog` obiektu, należy najpierw utworzyć obiekt przy użyciu `COlePropertiesDialog` konstruktora. Po skonstruowaniu okna dialogowego Wywołaj `DoModal` funkcję członkowską, aby wyświetlić okno dialogowe i zezwolić użytkownikowi na modyfikowanie wszelkich właściwości elementu. `DoModal` Zwraca czy użytkownik wybrał opcję OK (IDOK) lub przycisk Anuluj (IDCANCEL). Oprócz przycisków OK i Anuluj istnieje przycisk Zastosuj. Gdy użytkownik wybierze Zastosuj, wszelkie zmiany wprowadzone do właściwości elementu dokumentu są stosowane do elementu, a jego obraz jest automatycznie aktualizowany, ale pozostaje aktywny.

Element członkowski danych [m_psh](#m_psh) jest wskaźnikiem do `PROPSHEETHEADER` struktury i w większości przypadków nie trzeba uzyskać do niego dostępu jawnie. Jedynym wyjątkiem jest konieczność dodatkowych stron właściwości wykraczających poza domyślne strony Ogólne, widok i łącza. W takim przypadku można zmodyfikować `m_psh` element członkowski danych w celu uwzględnienia stron niestandardowych przed wywołaniem `DoModal` funkcji członkowskiej.

Aby uzyskać więcej informacji na temat okien dialogowych OLE, zobacz [okna dialogowe artykuł w OLE](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COlePropertiesDialog`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxodlgs. h

## <a name="colepropertiesdialogcolepropertiesdialog"></a><a name="colepropertiesdialog"></a> COlePropertiesDialog::COlePropertiesDialog

Tworzy obiekt `COlePropertiesDialog`.

```
COlePropertiesDialog(
    COleClientItem* pItem,
    UINT nScaleMin = 10,
    UINT nScaleMax = 500,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametry

*pItem*<br/>
Wskaźnik do elementu dokumentu, którego właściwości są używane.

*nScaleMin*<br/>
Minimalny procent skalowania dla obrazu elementu dokumentu.

*nScaleMax*<br/>
Maksymalna wartość procentowa skalowania obrazu elementu dokumentu.

*pParentWnd*<br/>
Wskaźnik do elementu nadrzędnego lub właściciela okna dialogowego.

### <a name="remarks"></a>Uwagi

Utwórz wspólną klasę okna dialogowego właściwości obiektu OLE z `COlePropertiesDialog` , aby zaimplementować skalowanie dla elementów dokumentu. Wszystkie okna dialogowe zaimplementowane przez wystąpienie tej klasy nie będą obsługiwały skalowania elementu dokumentu.

Domyślnie okno dialogowe wspólne właściwości obiektu OLE ma trzy strony domyślne:

- Ogólne

   Ta strona zawiera informacje o systemie dla pliku reprezentowanego przez wybrany element dokumentu. Na tej stronie użytkownik może przekonwertować wybrany element na inny typ.

- Widok

   Ta strona zawiera opcje wyświetlania elementu, zmiany ikony i zmiany skalowania obrazu.

- Link

   Ta strona zawiera opcje zmiany lokalizacji połączonego elementu i zaktualizowania połączonego elementu. Na tej stronie użytkownik może przerwać łącze wybranego elementu.

Aby dodać strony poza tymi, które są udostępniane domyślnie, przed opuszczeniem konstruktora klasy pochodnej należy zmodyfikować zmienną członkowską [m_psh](#m_psh) `COlePropertiesDialog` . Jest to zaawansowana implementacja `COlePropertiesDialog` konstruktora.

## <a name="colepropertiesdialogdomodal"></a><a name="domodal"></a> COlePropertiesDialog::D oModal

Wywołaj tę funkcję elementu członkowskiego, aby wyświetlić okno dialogowe właściwości obiektu OLE systemu Windows i umożliwić użytkownikowi wyświetlanie i/lub zmienianie różnych właściwości elementu dokumentu.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Wartość zwracana

IDOK lub IDCANCEL, jeśli się to powiedzie; w przeciwnym razie 0. IDOK i IDCANCEL są stałymi, które wskazują, czy użytkownik zaznaczył przycisk OK lub Anuluj.

Jeśli IDCANCEL jest zwracany, można wywołać funkcję Windows [CommDlgExtendedError](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) , aby określić, czy wystąpił błąd.

## <a name="colepropertiesdialogm_gp"></a><a name="m_gp"></a> COlePropertiesDialog:: m_gp

Struktura typu [OLEUIGNRLPROPS](/windows/win32/api/oledlg/ns-oledlg-oleuignrlpropsw)używana do inicjowania strony Ogólne w oknie dialogowym właściwości obiektu OLE.

```
OLEUIGNRLPROPS m_gp;
```

### <a name="remarks"></a>Uwagi

Ta strona zawiera typ i rozmiar osadzania i umożliwia użytkownikowi dostęp do okna dialogowego Konwersja. Ta strona pokazuje również lokalizację docelową linku, jeśli obiekt jest łączem.

Aby uzyskać więcej informacji na temat `OLEUIGNRLPROPS` struktury, zobacz Windows SDK.

## <a name="colepropertiesdialogm_lp"></a><a name="m_lp"></a> COlePropertiesDialog:: m_lp

Struktura typu [OLEUILINKPROPS](/windows/win32/api/oledlg/ns-oledlg-oleuilinkpropsw)użyta do zainicjowania strony łącza okna dialogowego właściwości obiektu OLE.

```
OLEUILINKPROPS m_lp;
```

### <a name="remarks"></a>Uwagi

Ta strona zawiera lokalizację połączonego elementu i umożliwia użytkownikowi aktualizowanie lub przerywanie łącza do elementu.

Aby uzyskać więcej informacji na temat `OLEUILINKPROPS` struktury, zobacz Windows SDK.

## <a name="colepropertiesdialogm_op"></a><a name="m_op"></a> COlePropertiesDialog:: m_op

Struktura typu [OLEUIOBJECTPROPS](/windows/win32/api/oledlg/ns-oledlg-oleuiobjectpropsw)użyta do zainicjowania typowego okna dialogowego właściwości obiektu OLE.

```
OLEUIOBJECTPROPS m_op;
```

### <a name="remarks"></a>Uwagi

Ta struktura zawiera elementy członkowskie używane do inicjowania stron ogólnych, linków i widoku.

Aby uzyskać więcej informacji, zobacz struktury OLEUIOBJECTPROPS i [OLEUILINKPROPS](/windows/win32/api/oledlg/ns-oledlg-oleuilinkpropsw) w Windows SDK.

## <a name="colepropertiesdialogm_psh"></a><a name="m_psh"></a> COlePropertiesDialog:: m_psh

Struktura typu [PROPSHEETHEADER](/windows/win32/api/prsht/ns-prsht-propsheetheadera_v2), której członkowie przechowują cechy obiektu okna dialogowego.

```
PROPSHEETHEADER m_psh;
```

### <a name="remarks"></a>Uwagi

Po skonstruowaniu `COlePropertiesDialog` obiektu można użyć, `m_psh` Aby ustawić różne aspekty okna dialogowego przed wywołaniem `DoModal` funkcji składowej.

W przypadku zmodyfikowania `m_psh` elementu członkowskiego danych należy zmienić zachowanie domyślne.

Aby uzyskać więcej informacji na temat `PROPSHEETHEADER` struktury, zobacz Windows SDK.

## <a name="colepropertiesdialogm_vp"></a><a name="m_vp"></a> COlePropertiesDialog:: m_vp

Struktura typu [OLEUIVIEWPROPS](/windows/win32/api/oledlg/ns-oledlg-oleuiviewpropsw)używana do inicjowania strony widoku okna dialogowego właściwości obiektu OLE.

```
OLEUIVIEWPROPS m_vp;
```

### <a name="remarks"></a>Uwagi

Ta strona zezwala użytkownikowi na przełączanie się między widokami "Content" i "Icon" obiektu oraz zmianę jego skalowania w kontenerze. Umożliwia także użytkownikowi dostęp do okna dialogowego Zmień ikonę, gdy obiekt jest wyświetlany jako ikona.

Aby uzyskać więcej informacji na temat `OLEUIVIEWPROPS` struktury, zobacz Windows SDK.

## <a name="colepropertiesdialogonapplyscale"></a><a name="onapplyscale"></a> COlePropertiesDialog::OnApplyScale

Wywoływane przez platformę, gdy wartość skalowania została zmieniona, a wybrano opcję OK lub Zastosuj.

```
virtual BOOL OnApplyScale(
    COleClientItem* pItem,
    int nCurrentScale,
    BOOL bRelativeToOrig);
```

### <a name="parameters"></a>Parametry

*pItem*<br/>
Wskaźnik do elementu dokumentu, którego właściwości są używane.

*nCurrentScale*<br/>
Wartość numeryczna skali okna dialogowego.

*bRelativeToOrig*<br/>
Wskazuje, czy skalowanie ma zastosowanie do oryginalnego rozmiaru elementu dokumentu.

### <a name="return-value"></a>Wartość zwracana

Wartość różna od zera, jeśli jest obsługiwana; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Domyślna implementacja nie robi nic. Należy zastąpić tę funkcję, aby włączyć kontrolki skalowania.

> [!NOTE]
> Przed wyświetleniem okna dialogowego wspólne właściwości obiektu OLE, struktura wywołuje tę funkcję z wartością NULL dla *pItem* i-1 dla *nCurrentScale*. Jest to wykonywane w celu ustalenia, czy kontrolki skalowania powinny być włączone.

## <a name="see-also"></a>Zobacz też

[Przykładowy cykl MFC](../../overview/visual-cpp-samples.md)<br/>
[Klasa COleDialog](../../mfc/reference/coledialog-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa COleDialog](../../mfc/reference/coledialog-class.md)<br/>
[Klasa CPropertyPage](../../mfc/reference/cpropertypage-class.md)

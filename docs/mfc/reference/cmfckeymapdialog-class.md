---
description: 'Dowiedz się więcej na temat: Klasa CMFCKeyMapDialog'
title: Klasa CMFCKeyMapDialog
ms.date: 11/04/2016
f1_keywords:
- CMFCKeyMapDialog
- AFXKEYMAPDIALOG/CMFCKeyMapDialog
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::CMFCKeyMapDialog
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::DoModal
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::FormatItem
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::GetCommandKeys
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnInsertItem
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnPrintHeader
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnPrintItem
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnSetColumns
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::PrintKeyMap
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::SetColumnsWidth
helpviewer_keywords:
- CMFCKeyMapDialog [MFC], CMFCKeyMapDialog
- CMFCKeyMapDialog [MFC], DoModal
- CMFCKeyMapDialog [MFC], FormatItem
- CMFCKeyMapDialog [MFC], GetCommandKeys
- CMFCKeyMapDialog [MFC], OnInsertItem
- CMFCKeyMapDialog [MFC], OnPrintHeader
- CMFCKeyMapDialog [MFC], OnPrintItem
- CMFCKeyMapDialog [MFC], OnSetColumns
- CMFCKeyMapDialog [MFC], PrintKeyMap
- CMFCKeyMapDialog [MFC], SetColumnsWidth
ms.assetid: 5feb4942-d636-462d-a162-0104dd320f4e
ms.openlocfilehash: e339edb54b9c381dd2b27c9ee3ec7566308ae434
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265236"
---
# <a name="cmfckeymapdialog-class"></a>Klasa CMFCKeyMapDialog

`CMFCKeyMapDialog`Klasa obsługuje kontrolkę, która mapuje polecenia do kluczy na klawiaturze.

## <a name="syntax"></a>Składnia

```
class CMFCKeyMapDialog : public CDialogEx
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCKeyMapDialog::CMFCKeyMapDialog](#cmfckeymapdialog)|Konstruuje `CMFCKeyMapDialog` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCKeyMapDialog::D oModal](#domodal)|Wyświetla okno dialogowe Mapowanie klawiatury.|

### <a name="protected-methods"></a>Metody chronione

|Nazwa|Opis|
|----------|-----------------|
|[CMFCKeyMapDialog::FormatItem](#formatitem)|Wywoływane przez platformę, aby skompilować ciąg opisujący mapowanie klucza. Domyślnie ciąg zawiera nazwę polecenia, używane klucze skrótów oraz opis klawisza skrótu.|
|[CMFCKeyMapDialog::GetCommandKeys](#getcommandkeys)|Pobiera ciąg zawierający listę klawiszy skrótów skojarzonych z określonym poleceniem.|
|[CMFCKeyMapDialog::OnInsertItem](#oninsertitem)|Wywoływane przez platformę przed wstawieniem nowego elementu do kontrolki listy wewnętrznej, która obsługuje kontrolkę mapowania klawiatury.|
|[CMFCKeyMapDialog::OnPrintHeader](#onprintheader)|Wywoływane przez platformę, aby wydrukować nagłówek dla mapy klawiatury na nowej stronie.|
|[CMFCKeyMapDialog::OnPrintItem](#onprintitem)|Wywoływane przez platformę w celu wydrukowania elementu mapowania klawiatury.|
|[CMFCKeyMapDialog::OnSetColumns](#onsetcolumns)|Wywoływane przez platformę, aby ustawić napisy dla kolumn w kontrolce listy wewnętrznej, która obsługuje kontrolkę mapowania klawiatury.|
|[CMFCKeyMapDialog::P rintKeyMap](#printkeymap)|Wywoływane przez platformę, gdy użytkownik kliknie przycisk **Drukuj** .|
|[CMFCKeyMapDialog::SetColumnsWidth](#setcolumnswidth)|Wywoływane przez platformę, aby ustawić szerokość kolumn w kontrolce listy wewnętrznej, która obsługuje kontrolkę mapowania klawiatury.|

## <a name="remarks"></a>Uwagi

Użyj `CMFCKeyMapDialog` klasy, aby zaimplementować okno dialogowe Mapowanie klawiatury o zmiennym rozmiarze. W oknie dialogowym zostanie wyświetlona lista skrótów klawiaturowych i skojarzonych z nimi poleceń.

Aby użyć `CMFCKeyMapDialog` klasy w aplikacji, Przekaż wskaźnik do głównego okna ramki jako parametr do `CMFCKeyMapDialog` konstruktora. Następnie Wywołaj `DoModal` metodę, aby uruchomić modalne okno dialogowe.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

[CMFCKeyMapDialog](../../mfc/reference/cmfckeymapdialog-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxkeymapdialog. h

## <a name="cmfckeymapdialogcmfckeymapdialog"></a><a name="cmfckeymapdialog"></a> CMFCKeyMapDialog::CMFCKeyMapDialog

Konstruuje `CMFCKeyMapDialog` obiekt.

```
CMFCKeyMapDialog(
    CFrameWnd* pWndParentFrame,
    BOOL bEnablePrint=FALSE);
```

### <a name="parameters"></a>Parametry

*pWndParentFrame*<br/>
podczas Wskaźnik do okna nadrzędnego `CMFCKeyMapDialog` obiektu.

*bEnablePrint*<br/>
podczas PRAWDA, jeśli można wydrukować listę klawiszy skrótów; w przeciwnym razie FALSE. Wartość domyślna to FALSE.

### <a name="remarks"></a>Uwagi

### <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób konstruowania obiektu `CMFCKeyMapDialog` klasy. Ten przykład jest częścią [przykładu demonstracyjnego Visual Studio](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_VisualStudioDemo#21](../../mfc/codesnippet/cpp/cmfckeymapdialog-class_1.cpp)]

## <a name="cmfckeymapdialogdomodal"></a><a name="domodal"></a> CMFCKeyMapDialog::D oModal

Wyświetla okno dialogowe Mapowanie klawiatury.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Wartość zwracana

Liczba całkowita ze znakiem, taka jak IDOK lub IDCANCEL, która jest przenoszona do metody [CDialog:: zdarzenie EndDialog](../../mfc/reference/cdialog-class.md#enddialog) . Metoda z kolei zamyka okno dialogowe. Aby uzyskać więcej informacji, zobacz [CDialog::D omodal](../../mfc/reference/cdialog-class.md#domodal).

### <a name="remarks"></a>Uwagi

Okno dialogowe Mapowanie klawiatury umożliwia wybieranie i Przypisywanie klawiszy skrótów do różnych kategorii poleceń. Ponadto można skopiować wybrane klawisze akceleratora i ich opis do Schowka.

## <a name="cmfckeymapdialogformatitem"></a><a name="formatitem"></a> CMFCKeyMapDialog::FormatItem

Wywoływane przez platformę, aby skompilować ciąg opisujący mapowanie klucza. Domyślnie ciąg zawiera nazwę polecenia, używane klucze skrótów oraz opis klawisza skrótu.

```
virtual CString FormatItem(int nItem) const;
```

### <a name="parameters"></a>Parametry

*nItem*<br/>
podczas Indeks (liczony od zera) elementu na wewnętrznej liście mapowań kluczy.

### <a name="return-value"></a>Wartość zwracana

`CString`Obiekt, który zawiera tekst sformatowanego elementu.

### <a name="remarks"></a>Uwagi

## <a name="cmfckeymapdialoggetcommandkeys"></a><a name="getcommandkeys"></a> CMFCKeyMapDialog::GetCommandKeys

Pobiera wartość ciągu. Ciąg zawiera listę klawiszy skrótów, które są skojarzone z określonym poleceniem.

```
virtual CString GetCommandKeys(UINT uiCmdID) const;
```

### <a name="parameters"></a>Parametry

*uiCmdID*<br/>
podczas Identyfikator polecenia.

### <a name="return-value"></a>Wartość zwracana

Rozdzielana średnikami lista klawiszy skrótów, które są skojarzone z określonym poleceniem.

### <a name="remarks"></a>Uwagi

## <a name="cmfckeymapdialogoninsertitem"></a><a name="oninsertitem"></a> CMFCKeyMapDialog::OnInsertItem

Wywoływane przez platformę, zanim nowy element zostanie wstawiony do wewnętrznego formantu listy, który obsługuje kontrolkę mapowania klawiatury.

```
virtual void OnInsertItem(
    CMFCToolBarButton* pButton,
    int nItem);
```

### <a name="parameters"></a>Parametry

*pButton*<br/>
podczas Wskaźnik do przycisku paska narzędzi, który jest używany do mapowania kombinacji klawiszy klawiatury do nazwy polecenia i opisu. Element mapy kluczy jest przechowywany w wewnętrznej kontrolce listy.

*nItem*<br/>
podczas Indeks (liczony od zera) określający miejsce wstawienia nowego elementu mapy kluczy w wewnętrznej kontrolce listy.

### <a name="remarks"></a>Uwagi

## <a name="cmfckeymapdialogonprintheader"></a><a name="onprintheader"></a> CMFCKeyMapDialog::OnPrintHeader

Wywoływane przez platformę, aby wydrukować nagłówek dla mapy klawiatury na nowej stronie.

```
virtual int OnPrintHeader(
    CDC& dc,
    int nPage,
    int cx) const;
```

### <a name="parameters"></a>Parametry

*DC*<br/>
podczas Kontekst urządzenia dla drukarki.

*nPage*<br/>
podczas Numer strony do wydrukowania.

*CX*<br/>
podczas Przesunięcie w poziomie nagłówka (w pikselach).

### <a name="return-value"></a>Wartość zwracana

Jeśli to się powiedzie, Wysokość drukowanego tekstu. Aby uzyskać więcej informacji, zobacz sekcję zwracanej wartości w obszarze [przechwytywania::D rawtext](../../mfc/reference/cdc-class.md#drawtext).

### <a name="remarks"></a>Uwagi

Struktura używa tej metody do drukowania mapy klawiatury. Domyślnie ta metoda drukuje numer strony, nazwę aplikacji i tytuł okna dialogowego.

## <a name="cmfckeymapdialogonprintitem"></a><a name="onprintitem"></a> CMFCKeyMapDialog::OnPrintItem

Wywoływane przez platformę w celu wydrukowania elementu mapowania klawiatury.

```
virtual int OnPrintItem(
    CDC& dc,
    int nItem,
    int y,
    int cx,
    BOOL bCalcHeight) const;
```

### <a name="parameters"></a>Parametry

*DC*<br/>
podczas Kontekst urządzenia drukarki.

*nItem*<br/>
podczas Indeks (liczony od zera) elementu do wydrukowania.

*Y*<br/>
podczas Przesunięcie w pionie między górą strony a pozycją elementu.

*CX*<br/>
podczas Przesunięcie w poziomie między lewą krawędzią strony a pozycją elementu.

*bCalcHeight*<br/>
podczas Wartość TRUE, aby obliczyć najlepszą wysokość dla elementu drukowania; Wartość FALSE powoduje obcinanie elementu Print, tak aby pasował do obszaru domyślnego.

### <a name="return-value"></a>Wartość zwracana

Wysokość wydrukowanego elementu.

### <a name="remarks"></a>Uwagi

Struktura wywołuje tę metodę, aby wydrukować element okna dialogowego mapy kluczy. Domyślnie ta metoda drukuje nazwę polecenia elementu, skróty klawiaturowe i opis polecenia.

## <a name="cmfckeymapdialogonsetcolumns"></a><a name="onsetcolumns"></a> CMFCKeyMapDialog::OnSetColumns

Wywoływane przez platformę, aby ustawić napisy dla kolumn w kontrolce listy wewnętrznej, która obsługuje kontrolkę mapowania klawiatury.

```
virtual void OnSetColumns();
```

### <a name="remarks"></a>Uwagi

Domyślnie ta metoda uzyskuje podpisy dla kolumn z trzech zasobów. Podpis kolumny polecenia pochodzi z IDS_AFXBARRES_COMMAND, podpis kolumny klucza pochodzi z IDS_AFXBARRES_KEYS, a nagłówek kolumny opis pochodzi z IDS_AFXBARRES_DESCRIPTION.

## <a name="cmfckeymapdialogprintkeymap"></a><a name="printkeymap"></a> CMFCKeyMapDialog::P rintKeyMap

Wywoływane przez platformę, gdy użytkownik kliknie przycisk **Drukuj** .

```
virtual void PrintKeyMap();
```

### <a name="remarks"></a>Uwagi

`PrintKeyMap`Metoda drukuje mapę kluczy. Inicjuje nowe zadanie drukowania, a następnie wielokrotnie wywołuje metody [CMFCKeyMapDialog:: OnPrintHeader](#onprintheader) i [CMFCKeyMapDialog:: OnPrintItem](#onprintitem) do momentu wydrukowania wszystkich mapowań kluczy.

## <a name="cmfckeymapdialogsetcolumnswidth"></a><a name="setcolumnswidth"></a> CMFCKeyMapDialog::SetColumnsWidth

Wywoływane przez platformę, aby ustawić szerokość kolumn w kontrolce listy wewnętrznej, która obsługuje kontrolkę mapowania klawiatury.

```
virtual void SetColumnsWidth();
```

### <a name="remarks"></a>Uwagi

Ta metoda ustawia kolumny wewnętrznej kontrolki listy na szerokości domyślne. Najpierw jest obliczana szerokość kolumny klawiszy skrótów. Następnie jedna trzecia pozostała szerokość jest przypisana do kolumny polecenia, a pozostałe dwie trzecie są przydzieleni do kolumny Description.

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)

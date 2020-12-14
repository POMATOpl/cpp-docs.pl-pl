---
description: Dowiedz się więcej o strukturze CPrintInfo
title: CPrintInfo, struktura
ms.date: 11/04/2016
f1_keywords:
- CPrintInfo
helpviewer_keywords:
- CPrintInfo structure [MFC]
ms.assetid: 0b3de849-d050-4386-9a14-f4c1a25684f7
ms.openlocfilehash: 355bcf2f04b32756ae16147465054e945d70cf78
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343391"
---
# <a name="cprintinfo-structure"></a>CPrintInfo, struktura

Przechowuje informacje o zadaniu drukowania lub drukowania w wersji zapoznawczej.

## <a name="syntax"></a>Składnia

```
struct CPrintInfo
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CPrintInfo::GetFromPage](#getfrompage)|Zwraca numer pierwszej drukowanej strony.|
|[CPrintInfo::GetMaxPage](#getmaxpage)|Zwraca numer ostatniej strony dokumentu.|
|[CPrintInfo::GetMinPage](#getminpage)|Zwraca numer pierwszej strony dokumentu.|
|[CPrintInfo::GetOffsetPage](#getoffsetpage)|Zwraca liczbę stron poprzedzających pierwszą stronę elementu DocObject drukowanego w połączonym zadaniu drukowania DocObject.|
|[CPrintInfo::GetToPage](#gettopage)|Zwraca numer ostatniej drukowanej strony.|
|[CPrintInfo::SetMaxPage](#setmaxpage)|Ustawia numer ostatniej strony dokumentu.|
|[CPrintInfo::SetMinPage](#setminpage)|Ustawia numer pierwszej strony dokumentu.|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CPrintInfo:: m_bContinuePrinting](#m_bcontinueprinting)|Zawiera flagę wskazującą, czy platforma powinna kontynuować pętlę drukowania.|
|[CPrintInfo:: m_bDirect](#m_bdirect)|Zawiera flagę wskazującą, czy dokument jest drukowany bezpośrednio (bez wyświetlania okna dialogowego drukowania).|
|[CPrintInfo:: m_bDocObject](#m_bdocobject)|Zawiera flagę wskazującą, czy dokument jest drukowany jest DocObject.|
|[CPrintInfo:: m_bPreview](#m_bpreview)|Zawiera flagę wskazującą, czy dokument jest w wersji zapoznawczej.|
|[CPrintInfo:: m_dwFlags](#m_dwflags)|Określa operacje drukowania DocObject.|
|[CPrintInfo:: m_lpUserData](#m_lpuserdata)|Zawiera wskaźnik do struktury utworzonej przez użytkownika.|
|[CPrintInfo:: m_nCurPage](#m_ncurpage)|Określa numer aktualnie drukowanej strony.|
|[CPrintInfo:: m_nJobNumber](#m_njobnumber)|Określa numer zadania przypisanego przez system operacyjny dla bieżącego zadania drukowania|
|[CPrintInfo:: m_nNumPreviewPages](#m_nnumpreviewpages)|Określa liczbę stron wyświetlanych w oknie podglądu; 1 lub 2.|
|[CPrintInfo:: m_nOffsetPage](#m_noffsetpage)|Określa przesunięcie określonej pierwszej strony DocObject w połączonym zadaniu drukowania DocObject.|
|[CPrintInfo:: m_pPD](#m_ppd)|Zawiera wskaźnik do `CPrintDialog` obiektu używanego do drukowania okna dialogowego.|
|[CPrintInfo:: m_rectDraw](#m_rectdraw)|Określa prostokąt definiujący bieżący użyteczny obszar strony.|
|[CPrintInfo:: m_strPageDesc](#m_strpagedesc)|Zawiera ciąg formatu dla wyświetlania numerów stron.|

## <a name="remarks"></a>Uwagi

`CPrintInfo` jest strukturą i nie ma klasy bazowej.

Struktura tworzy obiekt za `CPrintInfo` każdym razem, gdy wybrane zostanie polecenie Drukuj lub Podgląd wydruku i zniszczy je po zakończeniu polecenia.

`CPrintInfo` zawiera informacje o zadaniu drukowania jako całości, takie jak zakres stron do wydrukowania oraz bieżący stan zadania drukowania, na przykład aktualnie drukowane strony. Niektóre informacje są przechowywane w skojarzonym obiekcie [CPrintDialog](../../mfc/reference/cprintdialog-class.md) ; Ten obiekt zawiera wartości wprowadzone przez użytkownika w oknie dialogowym drukowania.

`CPrintInfo`Obiekt jest przesyłany między strukturą i klasą widoku podczas procesu drukowania i jest używany do wymiany informacji między nimi. Na przykład struktura informuje klasę widoku, która strona dokumentu ma być drukowana przez przypisanie wartości do `m_nCurPage` elementu członkowskiego `CPrintInfo` ; Klasa widoku Pobiera wartość i wykonuje rzeczywiste drukowanie określonej strony.

Innym przykładem jest przypadek, w którym długość dokumentu nie jest znana do momentu wydrukowania. W tej sytuacji Klasa widoku sprawdza koniec dokumentu przy każdej drukowaniu strony. Po osiągnięciu końca, Klasa widoku ustawia `m_bContinuePrinting` element członkowski `CPrintInfo` na wartość false; to informuje platformę, aby zatrzymać pętlę drukowania.

`CPrintInfo` jest używany przez funkcje składowe `CView` wymienione w obszarze "Zobacz też". Aby uzyskać więcej informacji na temat architektury drukowania dostarczonej przez biblioteka MFC, zobacz [okna ramek](../../mfc/frame-windows.md) i [Architektura dokumentu/widoku](../../mfc/document-view-architecture.md) oraz artykuły [drukowania](../../mfc/printing.md) i [drukowania: dokumenty wielostronicowe](../../mfc/multipage-documents.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`CPrintInfo`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxext. h

## <a name="cprintinfogetfrompage"></a><a name="getfrompage"></a> CPrintInfo::GetFromPage

Wywołaj tę funkcję, aby pobrać numer pierwszej strony do wydrukowania.

```
UINT GetFromPage() const;
```

### <a name="return-value"></a>Wartość zwracana

Numer pierwszej strony do wydrukowania.

### <a name="remarks"></a>Uwagi

Jest to wartość określona przez użytkownika w oknie dialogowym Drukowanie, która jest przechowywana w `CPrintDialog` obiekcie, do którego odwołuje się `m_pPD` element członkowski. Jeśli użytkownik nie określił wartości, wartością domyślną jest pierwsza strona dokumentu.

## <a name="cprintinfogetmaxpage"></a><a name="getmaxpage"></a> CPrintInfo::GetMaxPage

Wywołaj tę funkcję, aby pobrać numer ostatniej strony dokumentu.

```
UINT GetMaxPage() const;
```

### <a name="return-value"></a>Wartość zwracana

Numer ostatniej strony dokumentu.

### <a name="remarks"></a>Uwagi

Ta wartość jest przechowywana w `CPrintDialog` obiekcie, do którego odwołuje się `m_pPD` element członkowski.

## <a name="cprintinfogetminpage"></a><a name="getminpage"></a> CPrintInfo::GetMinPage

Wywołaj tę funkcję, aby pobrać numer pierwszej strony dokumentu.

```
UINT GetMinPage() const;
```

### <a name="return-value"></a>Wartość zwracana

Numer pierwszej strony dokumentu.

### <a name="remarks"></a>Uwagi

Ta wartość jest przechowywana w `CPrintDialog` obiekcie, do którego odwołuje się `m_pPD` element członkowski.

## <a name="cprintinfogetoffsetpage"></a><a name="getoffsetpage"></a> CPrintInfo::GetOffsetPage

Wywołaj tę funkcję, aby pobrać przesunięcie podczas drukowania wielu elementów DocObject z klienta DocObject.

```
UINT GetOffsetPage() const;
```

### <a name="return-value"></a>Wartość zwracana

Liczba stron poprzedzających pierwszą stronę elementu DocObject drukowanych w połączonym zadaniu drukowania DocObject.

### <a name="remarks"></a>Uwagi

Ta wartość jest przywoływana przez `m_nOffsetPage` element członkowski. Na pierwszej stronie dokumentu zostanie ponumerowana `m_nOffsetPage` wartość + 1 podczas drukowania jako DocObject z innymi aktywnymi dokumentami. `m_nOffsetPage`Element członkowski jest prawidłowy tylko wtedy, gdy `m_bDocObject` wartość jest równa true.

## <a name="cprintinfogettopage"></a><a name="gettopage"></a> CPrintInfo::GetToPage

Wywołaj tę funkcję, aby pobrać numer ostatniej strony do wydrukowania.

```
UINT GetToPage() const;
```

### <a name="return-value"></a>Wartość zwracana

Numer ostatniej strony do wydrukowania.

### <a name="remarks"></a>Uwagi

Jest to wartość określona przez użytkownika w oknie dialogowym Drukowanie, która jest przechowywana w `CPrintDialog` obiekcie, do którego odwołuje się `m_pPD` element członkowski. Jeśli użytkownik nie określił wartości, wartością domyślną jest Ostatnia strona dokumentu.

## <a name="cprintinfom_bcontinueprinting"></a><a name="m_bcontinueprinting"></a> CPrintInfo:: m_bContinuePrinting

Zawiera flagę wskazującą, czy platforma powinna kontynuować pętlę drukowania.

### <a name="remarks"></a>Uwagi

Jeśli wykonujesz stronicowanie w czasie drukowania, możesz ustawić dla tego elementu członkowskiego wartość FALSE w przesłonięciu, `CView::OnPrepareDC` gdy osiągnięto koniec dokumentu. Nie trzeba modyfikować tej zmiennej, jeśli określono długość dokumentu na początku zadania drukowania przy użyciu `SetMaxPage` funkcji elementu członkowskiego. `m_bContinuePrinting`Składowa jest zmienną publiczną typu bool.

## <a name="cprintinfom_bdirect"></a><a name="m_bdirect"></a> CPrintInfo:: m_bDirect

Struktura ustawia ten element członkowski na wartość TRUE, jeśli okno dialogowe drukowania zostanie pominięte na potrzeby drukowania bezpośredniego. W przeciwnym razie zwraca wartość FALSE.

### <a name="remarks"></a>Uwagi

Okno dialogowe drukowania jest zwykle pomijane podczas drukowania z powłoki lub podczas drukowania przy użyciu identyfikatora polecenia ID_FILE_PRINT_DIRECT.

Zwykle nie zmieniasz tego elementu członkowskiego, ale jeśli zmienisz go, zmień go przed wywołaniem [CView::D oprepareprinting](../../mfc/reference/cview-class.md#doprepareprinting) w przesłonięciu [CView:: OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting).

## <a name="cprintinfom_bdocobject"></a><a name="m_bdocobject"></a> CPrintInfo:: m_bDocObject

Zawiera flagę wskazującą, czy dokument jest drukowany jest DocObject.

### <a name="remarks"></a>Uwagi

Elementy członkowskie danych `m_dwFlags` i `m_nOffsetPage` są nieprawidłowe, chyba że ta flaga ma wartość true.

## <a name="cprintinfom_bpreview"></a><a name="m_bpreview"></a> CPrintInfo:: m_bPreview

Zawiera flagę wskazującą, czy dokument jest w wersji zapoznawczej.

### <a name="remarks"></a>Uwagi

Ta wartość jest ustawiana przez środowisko w zależności od tego, które polecenie zostało wykonane przez użytkownika. Okno dialogowe Drukowanie nie jest wyświetlane dla zadania drukowania w wersji zapoznawczej. `m_bPreview`Składowa jest zmienną publiczną typu bool.

## <a name="cprintinfom_dwflags"></a><a name="m_dwflags"></a> CPrintInfo:: m_dwFlags

Zawiera kombinację flag określających operacje drukowania DocObject.

### <a name="remarks"></a>Uwagi

Prawidłowy tylko wtedy, gdy element członkowski danych `m_bDocObject` ma wartość true.

Flagi mogą mieć co najmniej jedną z następujących wartości:

- PRINTFLAG_MAYBOTHERUSER

- PRINTFLAG_PROMPTUSER

- PRINTFLAG_USERMAYCHANGEPRINTER

- PRINTFLAG_RECOMPOSETODEVICE

- PRINTFLAG_DONTACTUALLYPRINT

- PRINTFLAG_FORCEPROPERTIES

- PRINTFLAG_PRINTTOFILE

## <a name="cprintinfom_lpuserdata"></a><a name="m_lpuserdata"></a> CPrintInfo:: m_lpUserData

Zawiera wskaźnik do struktury utworzonej przez użytkownika.

### <a name="remarks"></a>Uwagi

Służy do przechowywania danych specyficznych dla drukowania, które nie mają być przechowywane w klasie widoku. `m_lpUserData`Składowa jest zmienną publiczną typu LPVOID.

## <a name="cprintinfom_ncurpage"></a><a name="m_ncurpage"></a> CPrintInfo:: m_nCurPage

Zawiera numer bieżącej strony.

### <a name="remarks"></a>Uwagi

Struktura wywołuje `CView::OnPrepareDC` i `CView::OnPrint` jeden raz dla każdej strony dokumentu, określając inną wartość dla tego elementu członkowskiego za każdym razem; jego wartości mieszczą się w zakresie wartości zwracanej przez `GetFromPage` `GetToPage` . Użyj tego elementu członkowskiego w przesłonięciach `CView::OnPrepareDC` i, `CView::OnPrint` Aby wydrukować określoną stronę dokumentu.

Gdy tryb Podgląd jest wywoływany po raz pierwszy, struktura odczytuje wartość tego elementu członkowskiego, aby określić, która strona dokumentu powinna być wstępnie zapoznawcza. Możesz ustawić wartość tego elementu członkowskiego w przesłonięciu, `CView::OnPreparePrinting` Aby zachować bieżące położenie użytkownika w dokumencie podczas przechodzenia do trybu podglądu. `m_nCurPage`Składowa jest zmienną publiczną typu uint.

## <a name="cprintinfom_njobnumber"></a><a name="m_njobnumber"></a> CPrintInfo:: m_nJobNumber

Wskazuje numer zadania przypisany przez system operacyjny dla bieżącego zadania drukowania.

### <a name="remarks"></a>Uwagi

Ta wartość może być SP_ERROR, jeśli zadanie nie zostało jeszcze wydrukowane (oznacza to, że `CPrintInfo` obiekt jest nowo skonstruowany i nie był jeszcze używany do drukowania) lub jeśli wystąpił błąd podczas uruchamiania zadania.

## <a name="cprintinfom_nnumpreviewpages"></a><a name="m_nnumpreviewpages"></a> CPrintInfo:: m_nNumPreviewPages

Zawiera liczbę stron wyświetlanych w trybie podglądu; może mieć wartość 1 lub 2.

### <a name="remarks"></a>Uwagi

`m_nNumPreviewPages`Składowa jest zmienną publiczną typu uint.

## <a name="cprintinfom_noffsetpage"></a><a name="m_noffsetpage"></a> CPrintInfo:: m_nOffsetPage

Zawiera liczbę stron poprzedzających pierwszą stronę określonego DocObject w połączonym zadaniu drukowania DocObject.

## <a name="cprintinfom_ppd"></a><a name="m_ppd"></a> CPrintInfo:: m_pPD

Zawiera wskaźnik do `CPrintDialog` obiektu używanego do wyświetlania okna dialogowego drukowania dla zadania drukowania.

### <a name="remarks"></a>Uwagi

`m_pPD`Składowa jest zmienną publiczną zadeklarowaną jako wskaźnik do `CPrintDialog` .

## <a name="cprintinfom_rectdraw"></a><a name="m_rectdraw"></a> CPrintInfo:: m_rectDraw

Określa przydatny obszar rysowania strony we współrzędnych logicznych.

### <a name="remarks"></a>Uwagi

Można odwołać się do tego w przesłonięciu `CView::OnPrint` . Możesz użyć tego elementu członkowskiego, aby śledzić, który obszar pozostaje używany po drukowaniu nagłówków, stopek itd. `m_rectDraw`Element członkowski jest publiczną zmienną typu `CRect` .

## <a name="cprintinfom_strpagedesc"></a><a name="m_strpagedesc"></a> CPrintInfo:: m_strPageDesc

Zawiera ciąg formatu używany do wyświetlania numerów stron podczas podglądu wydruku; Ten ciąg składa się z dwóch podciągów, jeden do wyświetlania jednostronicowego i jeden do wyświetlania dwustronicowego, z których każda kończy się znakiem "\n".

### <a name="remarks"></a>Uwagi

Jako wartość domyślna w strukturze jest stosowany "Strona%u\nPages% u-%u\n". Jeśli chcesz użyć innego formatu numerów stron, Określ ciąg formatu w przesłonięciu `CView::OnPreparePrinting` . `m_strPageDesc`Element członkowski jest publiczną zmienną typu `CString` .

## <a name="cprintinfosetmaxpage"></a><a name="setmaxpage"></a> CPrintInfo::SetMaxPage

Wywołaj tę funkcję, aby określić numer ostatniej strony dokumentu.

```cpp
void SetMaxPage(UINT nMaxPage);
```

### <a name="parameters"></a>Parametry

*nMaxPage*<br/>
Numer ostatniej strony dokumentu.

### <a name="remarks"></a>Uwagi

Ta wartość jest przechowywana w `CPrintDialog` obiekcie, do którego odwołuje się `m_pPD` element członkowski. Jeśli długość dokumentu jest znana przed wydrukowaniem, Wywołaj tę funkcję z przesłonięcia `CView::OnPreparePrinting` . Jeśli długość dokumentu zależy od ustawienia określonego przez użytkownika w oknie dialogowym Drukowanie, Wywołaj tę funkcję z przesłonięcia `CView::OnBeginPrinting` . Jeśli długość dokumentu nie jest znana do momentu jego wydrukowania, użyj `m_bContinuePrinting` elementu członkowskiego, aby kontrolować pętlę drukowania.

### <a name="example"></a>Przykład

  Zobacz przykład dla [CView:: OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting).

## <a name="cprintinfosetminpage"></a><a name="setminpage"></a> CPrintInfo::SetMinPage

Wywołaj tę funkcję, aby określić numer pierwszej strony dokumentu.

```cpp
void SetMinPage(UINT nMinPage);
```

### <a name="parameters"></a>Parametry

*nMinPage*<br/>
Numer pierwszej strony dokumentu.

### <a name="remarks"></a>Uwagi

Numery stron zwykle zaczynają się od 1. Ta wartość jest przechowywana w `CPrintDialog` obiekcie, do którego odwołuje się `m_pPD` element członkowski.

## <a name="see-also"></a>Zobacz też

[Przykład DIBLOOK MFC](../../overview/visual-cpp-samples.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[CView:: OnBeginPrinting](../../mfc/reference/cview-class.md#onbeginprinting)<br/>
[CView:: OnEndPrinting](../../mfc/reference/cview-class.md#onendprinting)<br/>
[CView:: OnEndPrintPreview](../../mfc/reference/cview-class.md#onendprintpreview)<br/>
[CView:: OnPrepareDC](../../mfc/reference/cview-class.md#onpreparedc)<br/>
[CView:: OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting)<br/>
[CView:: OnPrint](../../mfc/reference/cview-class.md#onprint)

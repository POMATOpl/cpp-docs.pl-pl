---
description: 'Dowiedz się więcej na temat: Klasa CPrintDialogEx'
title: Klasa CPrintDialogEx
ms.date: 11/04/2016
f1_keywords:
- CPrintDialogEx
- AFXDLGS/CPrintDialogEx
- AFXDLGS/CPrintDialogEx::CPrintDialogEx
- AFXDLGS/CPrintDialogEx::CreatePrinterDC
- AFXDLGS/CPrintDialogEx::DoModal
- AFXDLGS/CPrintDialogEx::GetCopies
- AFXDLGS/CPrintDialogEx::GetDefaults
- AFXDLGS/CPrintDialogEx::GetDeviceName
- AFXDLGS/CPrintDialogEx::GetDevMode
- AFXDLGS/CPrintDialogEx::GetDriverName
- AFXDLGS/CPrintDialogEx::GetPortName
- AFXDLGS/CPrintDialogEx::GetPrinterDC
- AFXDLGS/CPrintDialogEx::PrintAll
- AFXDLGS/CPrintDialogEx::PrintCollate
- AFXDLGS/CPrintDialogEx::PrintCurrentPage
- AFXDLGS/CPrintDialogEx::PrintRange
- AFXDLGS/CPrintDialogEx::PrintSelection
- AFXDLGS/CPrintDialogEx::m_pdex
helpviewer_keywords:
- CPrintDialogEx [MFC], CPrintDialogEx
- CPrintDialogEx [MFC], CreatePrinterDC
- CPrintDialogEx [MFC], DoModal
- CPrintDialogEx [MFC], GetCopies
- CPrintDialogEx [MFC], GetDefaults
- CPrintDialogEx [MFC], GetDeviceName
- CPrintDialogEx [MFC], GetDevMode
- CPrintDialogEx [MFC], GetDriverName
- CPrintDialogEx [MFC], GetPortName
- CPrintDialogEx [MFC], GetPrinterDC
- CPrintDialogEx [MFC], PrintAll
- CPrintDialogEx [MFC], PrintCollate
- CPrintDialogEx [MFC], PrintCurrentPage
- CPrintDialogEx [MFC], PrintRange
- CPrintDialogEx [MFC], PrintSelection
- CPrintDialogEx [MFC], m_pdex
ms.assetid: 1d506703-ee1c-44cc-b4ce-4e778fec26b8
ms.openlocfilehash: 2f0d124422efa641c3ace833a5970b364a5cbc48
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301467"
---
# <a name="cprintdialogex-class"></a>Klasa CPrintDialogEx

Hermetyzuje usługi udostępniane przez arkusz właściwości drukowania systemu Windows.

## <a name="syntax"></a>Składnia

```
class CPrintDialogEx : public CCommonDialog
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CPrintDialogEx::CPrintDialogEx](#cprintdialogex)|Konstruuje `CPrintDialogEx` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CPrintDialogEx::CreatePrinterDC](#createprinterdc)|Tworzy kontekst urządzenia drukarki bez wyświetlania okna dialogowego Drukuj.|
|[CPrintDialogEx::D oModal](#domodal)|Wyświetla okno dialogowe i umożliwia użytkownikowi wybór wybranych opcji.|
|[CPrintDialogEx:: getkopiującs](#getcopies)|Pobiera żądaną liczbę kopii.|
|[CPrintDialogEx:: GetDefaults](#getdefaults)|Pobiera wartości domyślne urządzenia bez wyświetlania okna dialogowego.|
|[CPrintDialogEx:: GetDeviceName](#getdevicename)|Pobiera nazwę aktualnie wybranego urządzenia drukarki.|
|[CPrintDialogEx:: getdevmode](#getdevmode)|Pobiera `DEVMODE` strukturę.|
|[CPrintDialogEx:: GetDriverName](#getdrivername)|Pobiera nazwę sterownika urządzenia drukarki zdefiniowanego przez system.|
|[CPrintDialogEx:: GetPortName](#getportname)|Pobiera nazwę aktualnie wybranego portu drukarki.|
|[CPrintDialogEx::GetPrinterDC](#getprinterdc)|Pobiera uchwyt do kontekstu urządzenia drukarki.|
|[CPrintDialogEx::P rintAll](#printall)|Określa, czy wydrukować wszystkie strony dokumentu.|
|[CPrintDialogEx::P rintCollate](#printcollate)|Określa, czy posortowane kopie są wymagane.|
|[CPrintDialogEx::P rintCurrentPage](#printcurrentpage)|Określa, czy ma być drukowana bieżąca strona dokumentu.|
|[CPrintDialogEx::P rintRange](#printrange)|Określa, czy drukować tylko określony zakres stron.|
|[CPrintDialogEx::P rintSelection](#printselection)|Określa, czy drukować tylko aktualnie wybrane elementy.|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CPrintDialogEx:: m_pdex](#m_pdex)|Struktura używana do dostosowywania `CPrintDialogEx` obiektu.|

## <a name="remarks"></a>Uwagi

Możesz polegać na architekturze do obsługi wielu aspektów procesu drukowania aplikacji. Aby uzyskać więcej informacji o używaniu struktury do obsługi zadań drukowania, zobacz artykuł [Drukowanie](../../mfc/printing.md)artykułu.

Jeśli chcesz, aby aplikacja obsługiwała drukowanie bez zaangażowania platformy, możesz użyć `CPrintDialogEx` klasy "AS IS" z dostarczonym konstruktorem lub można utworzyć własną klasę dialogową z `CPrintDialogEx` i napisać konstruktora zgodnie z potrzebami. W obu przypadkach te okna dialogowe będą zachowywać się jak standardowe okna dialogowe MFC, ponieważ pochodzą z klasy `CCommonDialog` .

Aby użyć `CPrintDialogEx` obiektu, należy najpierw utworzyć obiekt przy użyciu `CPrintDialogEx` konstruktora. Po skonstruowaniu okna dialogowego można ustawić lub zmodyfikować dowolne wartości w strukturze [m_pdex](#m_pdex) , aby zainicjować wartości kontrolek okna dialogowego. `m_pdex`Struktura jest typu [PRINTDLGEX](/windows/win32/api/commdlg/ns-commdlg-printdlgexw). Aby uzyskać więcej informacji na temat tej struktury, zobacz Windows SDK.

Jeśli nie podasz własnych uchwytów `m_pdex` dla `hDevMode` `hDevNames` elementów i, pamiętaj, aby wywołać funkcję systemu Windows `GlobalFree` dla tych dojść po zakończeniu pracy z oknem dialogowym.

Po zainicjowaniu kontrolek okna dialogowego Wywołaj `DoModal` funkcję członkowską, aby wyświetlić okno dialogowe i umożliwić użytkownikowi wybranie opcji drukowania. Gdy `DoModal` zwraca, można określić, czy użytkownik zaznaczył przycisk OK, Zastosuj, czy Anuluj.

Jeśli użytkownik naciśnie przycisk OK, można użyć `CPrintDialogEx` funkcji elementów członkowskich, aby pobrać informacje wprowadzane przez użytkownika.

`CPrintDialogEx::GetDefaults`Funkcja członkowska jest przydatna do pobierania bieżących wartości domyślnych drukarki bez wyświetlania okna dialogowego. Ta metoda nie wymaga interakcji ze strony użytkownika.

Możesz użyć funkcji systemu Windows, `CommDlgExtendedError` Aby określić, czy wystąpił błąd podczas inicjowania okna dialogowego i dowiedzieć się więcej o błędzie. Aby uzyskać więcej informacji na temat tej funkcji, zobacz Windows SDK.

Aby uzyskać więcej informacji na temat korzystania z programu `CPrintDialogEx` , zobacz [wspólne klasy okien dialogowych](../../mfc/common-dialog-classes.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

`IObjectWithSite`

`IPrintDialogCallback`

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CPrintDialogEx`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxdlgs. h

## <a name="cprintdialogexcprintdialogex"></a><a name="cprintdialogex"></a> CPrintDialogEx::CPrintDialogEx

Konstruuje arkusz właściwości drukowania systemu Windows.

```
CPrintDialogEx(
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS       | PD_HIDEPRINTTOFILE | PD_NOSELECTION | PD_NOCURRENTPAGE,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametry

*flagiDW*<br/>
Jedna lub więcej flag, których można użyć, aby dostosować ustawienia okna dialogowego połączone przy użyciu operatora bitowego or. Na przykład flaga PD_ALLPAGES ustawia domyślny zakres drukowania na wszystkie strony dokumentu. Zapoznaj się ze strukturą [PRINTDLGEX](/windows/win32/api/commdlg/ns-commdlg-printdlgexw) w Windows SDK, aby uzyskać więcej informacji na temat tych flag.

*pParentWnd*<br/>
Wskaźnik do okna dialogowego nadrzędnego lub właściciela.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska tylko konstruuje obiekt. Użyj `DoModal` funkcji członkowskiej, aby wyświetlić okno dialogowe.

## <a name="cprintdialogexcreateprinterdc"></a><a name="createprinterdc"></a> CPrintDialogEx::CreatePrinterDC

Tworzy kontekst urządzenia drukarki (DC) dla struktury [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) i [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames) .

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>Wartość zwracana

Dojście do nowo utworzonego kontekstu urządzenia drukarki.

### <a name="remarks"></a>Uwagi

Zwrócony kontroler domeny również jest przechowywany w `hDC` członku [m_pdex](#m_pdex).

Przyjęto, że kontroler domeny jest bieżącym kontrolerem domeny, a wszystkie inne wcześniej uzyskane kontrolery domeny muszą zostać usunięte. Ta funkcja może być wywoływana, a wynikający z niego używany kontroler domeny bez wyświetlania okna dialogowego Drukuj.

## <a name="cprintdialogexdomodal"></a><a name="domodal"></a> CPrintDialogEx::D oModal

Wywołaj tę funkcję, aby wyświetlić arkusz właściwości drukowania systemu Windows i zezwolić użytkownikowi na wybór różnych opcji drukowania, takich jak liczba kopii, zakres stron i czy kopie mają być sortowane.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Wartość zwracana

Wartość zwracana INT_PTR to wynik HRESULT. Zapoznaj się z sekcją wartości zwracane w [PRINTDLGEX](/previous-versions/windows/desktop/legacy/ms646942\(v=vs.85\)) w Windows SDK.

### <a name="remarks"></a>Uwagi

Jeśli chcesz zainicjować różne opcje okna dialogowego drukowania przez ustawienie elementów członkowskich `m_pdex` struktury, należy to zrobić przed wywołaniem `DoModal` , ale po skonstruowaniu obiektu okna dialogowego.

Po wywołaniu `DoModal` można wywołać inne funkcje członkowskie, aby pobrać ustawienia lub dane wejściowe użytkownika w oknie dialogowym.

Jeśli flaga PD_RETURNDC jest używana podczas wywoływania `DoModal` , w `hDC` elemencie członkowskim [m_pdex](#m_pdex)zostanie zwrócony kontroler domeny. Ten kontroler domeny musi zostać zwolniony z wywołaniem [DeleteDC](/windows/win32/api/wingdi/nf-wingdi-deletedc) przez obiekt wywołujący `CPrintDialogEx` .

## <a name="cprintdialogexgetcopies"></a><a name="getcopies"></a> CPrintDialogEx:: getkopiującs

Wywołaj tę funkcję po wywołaniu `DoModal` , aby pobrać żądaną liczbę kopii.

```
int GetCopies() const;
```

### <a name="return-value"></a>Wartość zwracana

Liczba żądanych kopii.

## <a name="cprintdialogexgetdefaults"></a><a name="getdefaults"></a> CPrintDialogEx:: GetDefaults

Wywołaj tę funkcję, aby pobrać wartości domyślne urządzenia drukarki domyślnej bez wyświetlania okna dialogowego.

```
BOOL GetDefaults();
```

### <a name="return-value"></a>Wartość zwracana

Wartość TRUE, jeśli powodzenie, w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Tworzy kontekst urządzenia drukarki (DC) dla struktury [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) i [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames) .

`GetDefaults` nie wyświetla arkusza właściwości Print. Zamiast tego ustawia `hDevNames` `hDevMode` elementy i składowe [m_pdex](#m_pdex) do dojścia do struktur [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) i [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames) , które są inicjowane dla domyślnej drukarki systemowej. Oba `hDevNames` i `hDevMode` muszą mieć wartość null lub być `GetDefaults` niepowodzeniem.

Jeśli flaga PD_RETURNDC jest ustawiona, ta funkcja nie tylko zwróci `hDevNames` i `hDevMode` (znajduje się w `m_pdex.hDevNames` i `m_pdex.hDevMode` ) do obiektu wywołującego, ale zwróci również kontroler domeny w usłudze `m_pdex.hDC` . Obiekt wywołujący jest odpowiedzialny za usunięcie kontrolera domeny drukarki i wywołanie funkcji [GlobalFree](/windows/win32/api/winbase/nf-winbase-globalfree) systemu Windows na uchwytach po zakończeniu pracy z `CPrintDialogEx` obiektem.

## <a name="cprintdialogexgetdevicename"></a><a name="getdevicename"></a> CPrintDialogEx:: GetDeviceName

Wywołaj tę funkcję po wywołaniu [DoModal](#domodal) , aby pobrać nazwę aktualnie wybranej drukarki lub po wywołaniu metody [GetDefaults](#getdefaults) w celu pobrania nazwy drukarki domyślnej.

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>Wartość zwracana

Nazwa aktualnie zaznaczonej drukarki.

### <a name="remarks"></a>Uwagi

Użyj wskaźnika do `CString` obiektu zwróconego przez `GetDeviceName` jako wartość `lpszDeviceName` w wywołaniu metody [przechwytywania:: CreateDC](../../mfc/reference/cdc-class.md#createdc).

## <a name="cprintdialogexgetdevmode"></a><a name="getdevmode"></a> CPrintDialogEx:: getdevmode

Wywołaj tę funkcję po wywołaniu [DoModal](#domodal) lub [GetDefaults](#getdefaults) , aby pobrać informacje o urządzeniu drukującym.

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>Wartość zwracana

Struktura danych [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) , która zawiera informacje o inicjalizacji i środowisku urządzenia sterownika drukarki. Należy odblokować pamięć wykonywaną przez tę strukturę przy użyciu funkcji [GlobalUnlock](/windows/win32/api/winbase/nf-winbase-globalunlock) systemu Windows, która jest opisana w Windows SDK.

## <a name="cprintdialogexgetdrivername"></a><a name="getdrivername"></a> CPrintDialogEx:: GetDriverName

Wywołaj tę funkcję po wywołaniu [DoModal](#domodal) lub [GetDefaults](#getdefaults) , aby pobrać nazwę sterownika urządzenia drukarki zdefiniowanej przez system.

```
CString GetDriverName() const;
```

### <a name="return-value"></a>Wartość zwracana

`CString`Określanie nazwy sterownika zdefiniowanej przez system.

### <a name="remarks"></a>Uwagi

Użyj wskaźnika do `CString` obiektu zwróconego przez `GetDriverName` jako wartość elementu *lpszDriverName* w wywołaniu metody [przechwytywania:: CreateDC](../../mfc/reference/cdc-class.md#createdc).

## <a name="cprintdialogexgetportname"></a><a name="getportname"></a> CPrintDialogEx:: GetPortName

Wywołaj tę funkcję po wywołaniu [DoModal](#domodal) lub [GetDefaults](#getdefaults) , aby pobrać nazwę aktualnie wybranego portu drukarki.

```
CString GetPortName() const;
```

### <a name="return-value"></a>Wartość zwracana

Nazwa aktualnie wybranego portu drukarki.

## <a name="cprintdialogexgetprinterdc"></a><a name="getprinterdc"></a> CPrintDialogEx::GetPrinterDC

Zwraca uchwyt do kontekstu urządzenia drukarki.

```
HDC GetPrinterDC() const;
```

### <a name="return-value"></a>Wartość zwracana

Uchwyt do kontekstu urządzenia drukarki.

### <a name="remarks"></a>Uwagi

Należy wywołać funkcję [DeleteDC](/windows/win32/api/wingdi/nf-wingdi-deletedc) systemu Windows, aby usunąć kontekst urządzenia po jego zakończeniu.

## <a name="cprintdialogexm_pdex"></a><a name="m_pdex"></a> CPrintDialogEx:: m_pdex

Struktura PRINTDLGEX, której członkowie przechowują charakterystykę obiektu okna dialogowego.

```
PRINTDLGEX m_pdex;
```

### <a name="remarks"></a>Uwagi

Po skonstruowaniu `CPrintDialogEx` obiektu można użyć, `m_pdex` Aby ustawić różne aspekty okna dialogowego przed wywołaniem funkcji składowej [DoModal](#domodal) . Aby uzyskać więcej informacji na temat `m_pdex` struktury, zobacz [PRINTDLGEX](/windows/win32/api/commdlg/ns-commdlg-printdlgexw) w Windows SDK.

W przypadku zmodyfikowania `m_pdex` elementu członkowskiego danych należy zmienić zachowanie domyślne.

## <a name="cprintdialogexprintall"></a><a name="printall"></a> CPrintDialogEx::P rintAll

Wywołaj tę funkcję po wywołaniu `DoModal` , aby określić, czy wydrukować wszystkie strony w dokumencie.

```
BOOL PrintAll() const;
```

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli wszystkie strony w dokumencie mają być drukowane; w przeciwnym razie FALSE.

## <a name="cprintdialogexprintcollate"></a><a name="printcollate"></a> CPrintDialogEx::P rintCollate

Wywołaj tę funkcję po wywołaniu `DoModal` , aby określić, czy drukarka ma sortować wszystkie wydrukowane kopie dokumentu.

```
BOOL PrintCollate() const;
```

### <a name="return-value"></a>Wartość zwracana

Ma wartość TRUE, jeśli użytkownik wybierze pole wyboru COLLATE w oknie dialogowym. w przeciwnym razie FALSE.

## <a name="cprintdialogexprintcurrentpage"></a><a name="printcurrentpage"></a> CPrintDialogEx::P rintCurrentPage

Wywołaj tę funkcję po wywołaniu, `DoModal` Aby określić, czy chcesz wydrukować bieżącą stronę w dokumencie.

```
BOOL PrintCurrentPage() const;
```

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli w oknie dialogowym drukowania została wybrana **Bieżąca strona Drukuj** . w przeciwnym razie FALSE.

## <a name="cprintdialogexprintrange"></a><a name="printrange"></a> CPrintDialogEx::P rintRange

Wywołaj tę funkcję po wywołaniu `DoModal` , aby określić, czy drukować tylko zakres stron w dokumencie.

```
BOOL PrintRange() const;
```

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli drukowany jest tylko zakres stron w dokumencie; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Określone zakresy stron można określić na podstawie [m_pdex](#m_pdex) (zobacz `nPageRanges` , `nMaxPageRanges` i `lpPageRanges` w strukturze [PRINTDLGEX](/windows/win32/api/commdlg/ns-commdlg-printdlgexw) w Windows SDK).

## <a name="cprintdialogexprintselection"></a><a name="printselection"></a> CPrintDialogEx::P rintSelection

Wywołaj tę funkcję po wywołaniu `DoModal` , aby określić, czy drukować tylko aktualnie wybrane elementy.

```
BOOL PrintSelection() const;
```

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli tylko wybrane elementy mają być drukowane; w przeciwnym razie FALSE.

## <a name="see-also"></a>Zobacz też

[Klasa CCommonDialog](../../mfc/reference/ccommondialog-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[CPrintInfo, struktura](../../mfc/reference/cprintinfo-structure.md)

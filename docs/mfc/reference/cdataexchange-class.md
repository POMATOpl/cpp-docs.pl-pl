---
description: 'Dowiedz się więcej na temat: Klasa CDataExchange'
title: Klasa CDataExchange
ms.date: 11/04/2016
f1_keywords:
- CDataExchange
- AFXWIN/CDataExchange
- AFXWIN/CDataExchange::CDataExchange
- AFXWIN/CDataExchange::Fail
- AFXWIN/CDataExchange::PrepareCtrl
- AFXWIN/CDataExchange::PrepareEditCtrl
- AFXWIN/CDataExchange::PrepareOleCtrl
- AFXWIN/CDataExchange::m_bSaveAndValidate
- AFXWIN/CDataExchange::m_pDlgWnd
helpviewer_keywords:
- CDataExchange [MFC], CDataExchange
- CDataExchange [MFC], Fail
- CDataExchange [MFC], PrepareCtrl
- CDataExchange [MFC], PrepareEditCtrl
- CDataExchange [MFC], PrepareOleCtrl
- CDataExchange [MFC], m_bSaveAndValidate
- CDataExchange [MFC], m_pDlgWnd
ms.assetid: 84ed6113-325d-493e-a75d-223f03a992b8
ms.openlocfilehash: 36d11dc2b74142bd869b0e7b459d8bdb888b2cef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222180"
---
# <a name="cdataexchange-class"></a>Klasa CDataExchange

Obsługuje procedury wymiany danych w oknie dialogowym (DDX) i narzędzia sprawdzania poprawności danych (DDV) używane przez klasy Microsoft Foundation.

## <a name="syntax"></a>Składnia

```
class CDataExchange
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CDataExchange::CDataExchange](#cdataexchange)|Konstruuje `CDataExchange` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CDataExchange:: niepowodzenie](#fail)|Wywoływana, gdy Walidacja nie powiedzie się. Resetuje fokus do poprzedniej kontrolki i zgłasza wyjątek.|
|[CDataExchange::P repareCtrl](#preparectrl)|Przygotowuje określoną kontrolkę do wymiany danych lub walidacji. Użyj dla kontrolek nieedytowalnych.|
|[CDataExchange::P repareEditCtrl](#prepareeditctrl)|Przygotowuje określoną kontrolkę edycji do wymiany danych lub walidacji.|
|[CDataExchange::P repareOleCtrl](#prepareolectrl)|Przygotowuje określoną kontrolkę OLE do wymiany danych lub walidacji. Użyj dla kontrolek nieedytowalnych.|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CDataExchange:: m_bSaveAndValidate](#m_bsaveandvalidate)|Flaga dla kierunku DDX i DDV.|
|[CDataExchange:: m_pDlgWnd](#m_pdlgwnd)|Okno dialogowe lub okna, w którym odbywa się wymiana danych.|

## <a name="remarks"></a>Uwagi

`CDataExchange` nie ma klasy bazowej.

Użyj tej klasy, jeśli piszesz procedury wymiany danych dla niestandardowych typów danych lub kontrolek, lub jeśli piszesz własne procedury walidacji danych. Aby uzyskać więcej informacji na temat pisania własnych procedur DDX i DDV, zobacz [Uwagi techniczne 26](../../mfc/tn026-ddx-and-ddv-routines.md). Aby zapoznać się z omówieniem programów DDX i DDV, zobacz temat [wymiana i walidacja danych w oknie dialogowym](../../mfc/dialog-data-exchange-and-validation.md) [.](../../mfc/dialog-boxes.md)

`CDataExchange`Obiekt zawiera informacje kontekstowe, które są konieczne do DDX i DDV. Flaga *m_bSaveAndValidate* ma wartość false, gdy DDX jest używany do wypełnienia początkowych wartości formantów okna dialogowego z elementów członkowskich danych. Flaga *m_bSaveAndValidate* ma wartość true, jeśli DDX jest używany do ustawiania bieżących wartości formantów okna dialogowego w składowych danych i gdy DDV jest używany do walidacji wartości danych. Jeśli weryfikacja DDV nie powiedzie się, w procedurze DDV zostanie wyświetlone okno komunikatu z wyjaśnieniem błędu wejścia. Procedura DDV będzie następnie wywoływana w `Fail` celu zresetowania fokusu do kontrolowanej kontrolki i zgłoszenie wyjątku, aby zatrzymać proces walidacji.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`CDataExchange`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxwin. h

## <a name="cdataexchangecdataexchange"></a><a name="cdataexchange"></a> CDataExchange::CDataExchange

Wywołaj tę funkcję elementu członkowskiego, aby skonstruować `CDataExchange` obiekt.

```
CDataExchange(
    CWnd* pDlgWnd,
    BOOL bSaveAndValidate);
```

### <a name="parameters"></a>Parametry

*pDlgWnd*<br/>
Wskaźnik do okna nadrzędnego, który zawiera kontrolkę. Zwykle jest to obiekt pochodny [CDialog](../../mfc/reference/cdialog-class.md).

*bSaveAndValidate*<br/>
W przypadku opcji TRUE ten obiekt sprawdza poprawność danych, a następnie zapisuje dane z formantów do elementów członkowskich. W przypadku wartości FALSE ten obiekt przeniesie dane z elementów członkowskich do kontrolek.

### <a name="remarks"></a>Uwagi

Utwórz `CDataExchange` obiekt samodzielnie, aby przechowywać dodatkowe informacje w obiekcie wymiany danych w celu przekazania do [:D CWnd odataexchange](../../mfc/reference/cwnd-class.md#dodataexchange) funkcji członkowskiej.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCControlLadenDialog#70](../../mfc/codesnippet/cpp/cdataexchange-class_1.cpp)]

## <a name="cdataexchangefail"></a><a name="fail"></a> CDataExchange:: niepowodzenie

Struktura wywołuje tę funkcję członkowską, gdy operacja walidacji danych (DDV) okna dialogowego kończy się niepowodzeniem.

```cpp
void Fail();
```

### <a name="remarks"></a>Uwagi

`Fail` przywraca fokus i zaznaczenie do kontrolki, której Walidacja nie powiodła się (jeśli istnieje formant do przywrócenia). `Fail` następnie zgłasza wyjątek typu [CUserException](../../mfc/reference/cuserexception-class.md) , aby zatrzymać proces walidacji. Wyjątek powoduje wyświetlenie okna komunikatu z wyjaśnieniem błędu, który ma zostać wyświetlony. Po niepowodzeniu walidacji DDV użytkownik może ponownie wprowadzić dane w kontrolce, która ma problemy.

Implementacje niestandardowych procedur DDV mogą wywoływać `Fail` z ich procedur, gdy weryfikacja nie powiedzie się.

Aby uzyskać więcej informacji na temat pisania własnych procedur DDX i DDV, zobacz [Uwagi techniczne 26](../../mfc/tn026-ddx-and-ddv-routines.md). Aby zapoznać się z omówieniem DDX i DDV, zobacz temat [okno dialogowe wymiana danych i walidacja](../../mfc/dialog-data-exchange-and-validation.md) oraz okno [dialogowe](../../mfc/dialog-boxes.md).

## <a name="cdataexchangem_bsaveandvalidate"></a><a name="m_bsaveandvalidate"></a> CDataExchange:: m_bSaveAndValidate

Ta flaga wskazuje kierunek operacji wymiany danych okna dialogowego (DDX).

```
BOOL m_bSaveAndValidate;
```

### <a name="remarks"></a>Uwagi

Flaga jest różna od zera, jeśli `CDataExchange` obiekt jest używany do przenoszenia danych z kontrolek okna dialogowego do członków danych klasy okna dialogowego, gdy użytkownik edytuje kontrolki. Flaga ma wartość zero, jeśli obiekt jest używany do inicjowania formantów okna dialogowego z elementów członkowskich danych klasy okna dialogowego.

Flaga jest również nierówna zero podczas walidacji danych okna dialogowego (DDV).

Aby uzyskać więcej informacji na temat pisania własnych procedur DDX i DDV, zobacz [Uwagi techniczne 26](../../mfc/tn026-ddx-and-ddv-routines.md). Aby zapoznać się z omówieniem DDX i DDV, zobacz temat [okno dialogowe wymiana danych i walidacja](../../mfc/dialog-data-exchange-and-validation.md) oraz okno [dialogowe](../../mfc/dialog-boxes.md).

## <a name="cdataexchangem_pdlgwnd"></a><a name="m_pdlgwnd"></a> CDataExchange:: m_pDlgWnd

Zawiera wskaźnik do obiektu [CWnd](../../mfc/reference/cwnd-class.md) , dla którego odbywa się wymiana danych (DDX) lub Walidacja (DDV).

```
CWnd* m_pDlgWnd;
```

### <a name="remarks"></a>Uwagi

Ten obiekt jest zwykle obiektem [CDialog](../../mfc/reference/cdialog-class.md) . Implementacje procedur niestandardowych DDX lub DDV mogą używać tego wskaźnika, aby uzyskać dostęp do okna dialogowego, które zawiera kontrolki, na których działają.

Aby uzyskać więcej informacji na temat pisania własnych procedur DDX i DDV, zobacz [Uwagi techniczne 26](../../mfc/tn026-ddx-and-ddv-routines.md). Aby zapoznać się z omówieniem DDX i DDV, zobacz temat [okno dialogowe wymiana danych i walidacja](../../mfc/dialog-data-exchange-and-validation.md) oraz okno [dialogowe](../../mfc/dialog-boxes.md).

## <a name="cdataexchangepreparectrl"></a><a name="preparectrl"></a> CDataExchange::P repareCtrl

Struktura wywołuje tę funkcję elementu członkowskiego, aby przygotować określoną kontrolkę do wymiany danych (DDX) i walidacji (DDV).

```
HWND PrepareCtrl(int nIDC);
```

### <a name="parameters"></a>Parametry

*nIDC*<br/>
Identyfikator kontrolki, która ma zostać przygotowana do DDX lub DDV.

### <a name="return-value"></a>Wartość zwracana

Właściwość HWND kontrolki przygotowanej dla DDX lub DDV.

### <a name="remarks"></a>Uwagi

Zamiast tego użyj [PrepareEditCtrl](#prepareeditctrl) do edycji kontrolek; Użyj tej funkcji elementu członkowskiego dla wszystkich innych kontrolek.

Przygotowanie składa się z przechowywania wartości HWND kontrolki w `CDataExchange` klasie. Struktura używa tego uchwytu do przywrócenia fokusu do wcześniej skoncentrowanego formantu w przypadku awarii DDX lub DDV.

Implementacje procedur niestandardowych DDX lub DDV powinny wywoływać `PrepareCtrl` wszystkie kontrolki nieedytujące, dla których są wymieniane danymi za pośrednictwem DDX lub walidacji danych za pośrednictwem DDV.

Aby uzyskać więcej informacji na temat pisania własnych procedur DDX i DDV, zobacz [Uwagi techniczne 26](../../mfc/tn026-ddx-and-ddv-routines.md). Aby zapoznać się z omówieniem DDX i DDV, zobacz temat [okno dialogowe wymiana danych i walidacja](../../mfc/dialog-data-exchange-and-validation.md) oraz okno [dialogowe](../../mfc/dialog-boxes.md).

## <a name="cdataexchangeprepareeditctrl"></a><a name="prepareeditctrl"></a> CDataExchange::P repareEditCtrl

Struktura wywołuje tę funkcję członkowską w celu przygotowania określonej kontrolki edycji do wymiany danych (DDX) i walidacji (DDV).

```
HWND PrepareEditCtrl(int nIDC);
```

### <a name="parameters"></a>Parametry

*nIDC*<br/>
Identyfikator kontrolki edycji, która ma zostać przygotowana do DDX lub DDV.

### <a name="return-value"></a>Wartość zwracana

Właściwość HWND kontrolki edycji przygotowana do DDX lub DDV.

### <a name="remarks"></a>Uwagi

Zamiast tego użyj [PrepareCtrl](#preparectrl) dla wszystkich kontrolek, które nie są edytowane.

Przygotowanie składa się z dwóch rzeczy. Najpierw `PrepareEditCtrl` przechowuje Właściwość HWND kontrolki w `CDataExchange` klasie. Struktura używa tego uchwytu do przywrócenia fokusu do wcześniej skoncentrowanego formantu w przypadku awarii DDX lub DDV. Następnie `PrepareEditCtrl` ustawia flagę w klasie, `CDataExchange` Aby wskazać, że formant, którego dane są wymieniane lub sprawdzane jest kontrolka edycji.

Implementacje procedur niestandardowych DDX lub DDV powinny wywoływać `PrepareEditCtrl` wszystkie kontrolki edycji, dla których są wymieniane danymi za pośrednictwem DDX lub walidacji danych za pośrednictwem DDV.

Aby uzyskać więcej informacji na temat pisania własnych procedur DDX i DDV, zobacz [Uwagi techniczne 26](../../mfc/tn026-ddx-and-ddv-routines.md). Aby zapoznać się z omówieniem DDX i DDV, zobacz temat [okno dialogowe wymiana danych i walidacja](../../mfc/dialog-data-exchange-and-validation.md) oraz okno [dialogowe](../../mfc/dialog-boxes.md).

## <a name="cdataexchangeprepareolectrl"></a><a name="prepareolectrl"></a> CDataExchange::P repareOleCtrl

Struktura wywołuje tę funkcję elementu członkowskiego, aby przygotować określoną kontrolkę OLE do wymiany danych (DDX) i walidacji (DDV).

```
COleControlSite* PrepareOleCtrl(int nIDC);
```

### <a name="parameters"></a>Parametry

*nIDC*<br/>
Identyfikator kontrolki OLE, która ma zostać przygotowana do DDX lub DDV.

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do witryny kontrolki OLE.

### <a name="remarks"></a>Uwagi

Zamiast tego użyj [PrepareEditCtrl](#prepareeditctrl) dla kontrolek edycji lub [PrepareCtrl](#preparectrl) dla wszystkich innych formantów innych niż OLE.

Implementacje procedur niestandardowych DDX lub DDV powinny być wywoływane `PrepareOleCtrl` dla wszystkich kontrolek OLE, dla których są wymieniane danymi za pośrednictwem DDX lub walidacji danych za pośrednictwem DDV.

Aby uzyskać więcej informacji na temat pisania własnych procedur DDX i DDV, zobacz [Uwagi techniczne 26](../../mfc/tn026-ddx-and-ddv-routines.md). Aby zapoznać się z omówieniem DDX i DDV, zobacz temat [okno dialogowe wymiana danych i walidacja](../../mfc/dialog-data-exchange-and-validation.md) oraz okno [dialogowe](../../mfc/dialog-boxes.md).

## <a name="see-also"></a>Zobacz też

[Przykład VIEWEX MFC](../../overview/visual-cpp-samples.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[CWnd::D oDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange)<br/>
[CWnd:: UpdateData](../../mfc/reference/cwnd-class.md#updatedata)

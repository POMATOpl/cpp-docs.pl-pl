---
description: 'Dowiedz się więcej na temat: Klasa CClientDC —'
title: Klasa CClientDC —
ms.date: 11/04/2016
f1_keywords:
- CClientDC
- AFXWIN/CClientDC
- AFXWIN/CClientDC::CClientDC
- AFXWIN/CClientDC::m_hWnd
helpviewer_keywords:
- CClientDC [MFC], CClientDC
- CClientDC [MFC], m_hWnd
ms.assetid: 8a871d6b-06f8-496e-9fa3-9a5780848369
ms.openlocfilehash: 27735929734388ccb25eaf178e49d63884beed0d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122463"
---
# <a name="cclientdc-class"></a>Klasa CClientDC —

Należy zwrócić uwagę na wywołanie funkcji systemu Windows [GetDC —](/windows/win32/api/winuser/nf-winuser-getdc) w czasie konstruowania i [ReleaseDC](/windows/win32/api/winuser/nf-winuser-releasedc) w czasie niszczenia.

## <a name="syntax"></a>Składnia

```
class CClientDC : public CDC
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CClientDC —:: CClientDC —](#cclientdc)|Konstruuje `CClientDC` obiekt połączony z `CWnd` .|

### <a name="protected-data-members"></a>Chronione elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CClientDC —:: m_hWnd](#m_hwnd)|Właściwość HWND okna, dla którego `CClientDC` jest poprawna.|

## <a name="remarks"></a>Uwagi

Oznacza to, że kontekst urządzenia skojarzony z `CClientDC` obiektem jest obszar klienta okna.

Aby uzyskać więcej informacji na temat `CClientDC` , zobacz [konteksty urządzeń](../../mfc/device-contexts.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CClientDC`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxwin. h

## <a name="cclientdccclientdc"></a><a name="cclientdc"></a> CClientDC —:: CClientDC —

Tworzy `CClientDC` obiekt, który uzyskuje dostęp do obszaru klienckiego [CWnd](../../mfc/reference/cwnd-class.md) wskazywanym przez *pWnd*.

```
explicit CClientDC(CWnd* pWnd);
```

### <a name="parameters"></a>Parametry

*pWnd*<br/>
Okno, którego obszar klienta ma dostęp do obiektu kontekstu urządzenia.

### <a name="remarks"></a>Uwagi

Konstruktor wywołuje funkcję systemu Windows [GetDC —](/windows/win32/api/winuser/nf-winuser-getdc).

Wyjątek (typu `CResourceException` ) jest zgłaszany w przypadku `GetDC` niepowodzenia wywołania systemu Windows. Kontekst urządzenia może nie być dostępny, jeśli system Windows już przydzielił wszystkie dostępne konteksty urządzenia. Twoja aplikacja konkuruje dla pięciu wspólnych kontekstów wyświetlania dostępnych w danym momencie w systemie Windows.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCDocView#42](../../mfc/codesnippet/cpp/cclientdc-class_1.cpp)]

## <a name="cclientdcm_hwnd"></a><a name="m_hwnd"></a> CClientDC —:: m_hWnd

`HWND` `CWnd` Wskaźnik używany do konstruowania `CClientDC` obiektu.

```
HWND m_hWnd;
```

### <a name="remarks"></a>Uwagi

*m_hWnd* jest zmienną chronioną.

### <a name="example"></a>Przykład

  Zobacz przykład dla [CClientDC —:: CClientDC —](#cclientdc).

## <a name="see-also"></a>Zobacz też

[Przykładowy interfejs MDI MFC](../../overview/visual-cpp-samples.md)<br/>
[Klasa przechwytywania](../../mfc/reference/cdc-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa przechwytywania](../../mfc/reference/cdc-class.md)

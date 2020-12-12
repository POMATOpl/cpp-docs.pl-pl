---
description: 'Dowiedz się więcej na temat: Klasa CSimpleDialog'
title: Klasa CSimpleDialog
ms.date: 11/04/2016
f1_keywords:
- CSimpleDialog
- ATLWIN/ATL::CSimpleDialog
- ATLWIN/ATL::CSimpleDialog::DoModal
helpviewer_keywords:
- CSimpleDialog class
- CSimpleDialog class, modal dialog boxes in ATL
- dialog boxes, modal
- modal dialog boxes, ATL
ms.assetid: 2ae65cc9-4f32-4168-aecd-200b4a480fdf
ms.openlocfilehash: 50889c4387515c85cd3c6e53bf12e7c0494504ed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140650"
---
# <a name="csimpledialog-class"></a>Klasa CSimpleDialog

Ta klasa implementuje podstawowe modalne okno dialogowe.

## <a name="syntax"></a>Składnia

```
template <WORD t_wDlgTemplateID, BOOL t_bCenter = TRUE>
class CSimpleDialog : public CDialogImplBase
```

#### <a name="parameters"></a>Parametry

*t_wDlgTemplateID*

Identyfikator zasobu zasobu szablonu okna dialogowego.

*t_bCenter*<br/>
Ma wartość TRUE, jeśli obiekt okna dialogowego ma być wyśrodkowany w oknie właściciela; w przeciwnym razie FALSE.

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CSimpleDialog::D oModal](#domodal)|Tworzy modalne okno dialogowe.|

## <a name="remarks"></a>Uwagi

Implementuje modalne okno dialogowe z podstawowymi funkcjami. `CSimpleDialog` zapewnia obsługę tylko typowych formantów systemu Windows. Aby utworzyć i wyświetlić modalne okno dialogowe, Utwórz wystąpienie tej klasy, podając nazwę istniejącego szablonu zasobu dla okna dialogowego. Obiekt okna dialogowego jest zamykany, gdy użytkownik kliknie dowolny formant ze wstępnie zdefiniowaną wartością (na przykład IDOK lub IDCANCEL).

`CSimpleDialog` umożliwia tworzenie tylko modalnych okien dialogowych. `CSimpleDialog` zawiera procedurę okna dialogowego, która używa domyślnej mapy komunikatów do kierowania komunikatów do odpowiednich programów obsługi.

Aby uzyskać więcej informacji, zobacz [implementowanie okna dialogowego](../../atl/implementing-a-dialog-box.md) .

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`CDialogImplBase`

`CSimpleDialog`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlwin. h

## <a name="csimpledialogdomodal"></a><a name="domodal"></a> CSimpleDialog::D oModal

Wywołuje modalne okno dialogowe i zwraca wynik okna dialogowego po zakończeniu.

```
INT_PTR DoModal(HWND hWndParent = ::GetActiveWindow());
```

### <a name="parameters"></a>Parametry

*hWndParent*<br/>
Uchwyt do elementu nadrzędnego okna dialogowego. Jeśli nie podano wartości, element nadrzędny zostanie ustawiony na bieżące aktywne okno.

### <a name="return-value"></a>Wartość zwracana

Jeśli to się powiedzie, wartość zwracana jest IDENTYFIKATORem zasobu formantu, który odrzucił okno dialogowe.

Jeśli funkcja się nie powiedzie, zwracana wartość to-1. Aby uzyskać rozszerzone informacje o błędzie, wywołaj polecenie `GetLastError` .

### <a name="remarks"></a>Uwagi

Ta metoda obsługuje wszystkie interakcje z użytkownikiem, gdy okno dialogowe jest aktywne. To sprawia, że okno dialogowe jest modalne; oznacza to, że użytkownik nie może współdziałać z innymi oknami, dopóki okno dialogowe nie zostanie zamknięte.

## <a name="see-also"></a>Zobacz też

[Przegląd klas](../../atl/atl-class-overview.md)

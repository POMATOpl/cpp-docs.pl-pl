---
description: 'Dowiedz się więcej na temat: powiadomienia z kontrolki edycji wzbogaconej'
title: Powiadomienia z formantów edycji wzbogaconej
ms.date: 11/04/2016
helpviewer_keywords:
- messages [MFC], notification [MFC]
- CRichEditCtrl class [MFC], notifications
- rich edit controls [MFC], notifications
- notifications [MFC], from CRichEditCtrl
ms.assetid: eb5304fe-f4f3-4557-9ebf-3095dea383c4
ms.openlocfilehash: 83f76c2b0bf8c27d30d8c113fc1607f3cbd718fc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254797"
---
# <a name="notifications-from-a-rich-edit-control"></a>Powiadomienia z formantów edycji wzbogaconej

Komunikaty powiadomień zdarzenia mające wpływ na kontrolkę edycji wzbogaconej ([CRichEditCtrl](reference/cricheditctrl-class.md)). Mogą być przetwarzane przez okno nadrzędne lub, przy użyciu odbicia komunikatu, przez samą kontrolkę edycji wzbogaconej. Kontrolki edycji wzbogaconej obsługują wszystkie komunikaty powiadomień używane z kontrolkami edycji, a także kilka dodatkowych. Możesz określić, które wiadomości z powiadomieniem formant edycji wzbogaconej wysyła jego okno nadrzędne, ustawiając jego "maskę zdarzeń".

Aby ustawić maskę zdarzeń dla kontrolki edycji wzbogaconej, użyj funkcji składowej [SetEventMask](reference/cricheditctrl-class.md#seteventmask) . Można pobrać bieżącą maskę zdarzeń dla kontrolki edycji wzbogaconej przy użyciu funkcji składowej [GetEventMask —](reference/cricheditctrl-class.md#geteventmask) .

W poniższych akapitach wymieniono kilka konkretnych powiadomień i ich zastosowania:

- EN_MSGFILTER obsługi powiadomienia EN_MSGFILTER umożliwia klasy, kontrolki edycji wzbogaconej lub jej okna nadrzędnego, filtrowanie wszystkich danych wejściowych klawiatury i myszy do kontrolki. Program obsługi może zapobiec przetwarzaniu lub przetworzeniu komunikatu z klawiatury lub myszy albo zmienić komunikat, modyfikując określoną strukturę [MSGFILTER](/windows/win32/api/richedit/ns-richedit-msgfilter) .

- EN_PROTECTED obsłużyć EN_PROTECTED komunikat powiadomienia, aby wykryć, kiedy użytkownik próbuje zmodyfikować chroniony tekst. Aby oznaczyć zakres tekstu jako chroniony, można ustawić efekt chronionego znaku. Aby uzyskać więcej informacji, zobacz [Formatowanie znaków w formantach edycji wzbogaconej](character-formatting-in-rich-edit-controls.md).

- EN_DROPFILES można umożliwić użytkownikom upuszczanie plików w kontrolce edycji wzbogaconej, przetwarzając EN_DROPFILES komunikat powiadomienia. Określona struktura [ENDROPFILES](/windows/win32/api/richedit/ns-richedit-endropfiles) zawiera informacje o usuwanych plikach.

- EN_SELCHANGE aplikacja może wykryć, kiedy bieżące zaznaczenie zostanie zmienione przez przetworzenie EN_SELCHANGE komunikat powiadomienia. Komunikat powiadomienia określa strukturę [SELCHANGE](/windows/win32/api/richedit/ns-richedit-selchange) zawierającą informacje o nowym zaznaczeniu.

## <a name="see-also"></a>Zobacz też

[Korzystanie z CRichEditCtrl](using-cricheditctrl.md)<br/>
[Formanty](controls-mfc.md)

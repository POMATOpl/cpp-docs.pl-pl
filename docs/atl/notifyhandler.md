---
description: 'Dowiedz się więcej na temat: NotifyHandler'
title: NotifyHandler
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- NotifyHandler function
ms.assetid: 5ff953ec-de35-42bc-8b3c-d384d636c139
ms.openlocfilehash: 1c08eaa91962fa9f6acf330de89334ad1224e582
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159378"
---
# <a name="notifyhandler"></a>NotifyHandler

Nazwa funkcji identyfikowanej przez trzeci parametr makra NOTIFY_HANDLER w mapie wiadomości.

## <a name="syntax"></a>Składnia

```cpp
LRESULT NotifyHandler(
    int idCtrl,
    LPNMHDR pnmh,
    BOOL& bHandled);
```

#### <a name="parameters"></a>Parametry

*idCtrl*<br/>
Identyfikator kontrolki wysyłającej wiadomość.

*pnmh*<br/>
Adres struktury [NMHDR](/windows/win32/api/richedit/ns-richedit-nmhdr) , która zawiera kod powiadomienia i dodatkowe informacje. W przypadku niektórych komunikatów powiadomień ten parametr wskazuje większą strukturę, która ma `NMHDR` strukturę jako pierwszy element członkowski.

*bHandled*<br/>
Mapa komunikatów ustawia *bHandled* na true przed wywołaniem *NotifyHandler* . Jeśli *NotifyHandler* nie obsługuje w pełni komunikatu, należy ustawić **wartość false** dla *bHandled* , aby wskazać, że komunikat musi zostać przetworzony.

## <a name="return-value"></a>Wartość zwracana

Wynik przetwarzania komunikatów. 0 w przypadku powodzenia.

## <a name="remarks"></a>Uwagi

Przykład użycia tego programu obsługi komunikatów w mapie komunikatów znajduje się w temacie [NOTIFY_HANDLER](reference/message-map-macros-atl.md#notify_handler)).

## <a name="see-also"></a>Zobacz też

[Implementowanie okna](../atl/implementing-a-window.md)<br/>
[Mapy komunikatów](../atl/message-maps-atl.md)<br/>
[WM_NOTIFY](/windows/win32/controls/wm-notify)

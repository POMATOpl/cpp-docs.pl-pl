---
description: 'Dowiedz się więcej na temat: CommandHandler — obiekt'
title: CommandHandler
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- CommandHandler function
ms.assetid: 662bc7bf-4a10-42b3-986d-d8bae4f63551
ms.openlocfilehash: 746048dd83088cac8316cf6e0140644956c21b4b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153287"
---
# <a name="commandhandler"></a>CommandHandler

`CommandHandler` jest funkcją identyfikowaną przez trzeci parametr makra COMMAND_HANDLER w mapie wiadomości.

## <a name="syntax"></a>Składnia

```cpp
LRESULT CommandHandler(
    WORD wNotifyCode,
    WORD wID,
    HWND hWndCtl,
    BOOL& bHandled);
```

#### <a name="parameters"></a>Parametry

*Włącz wNotifyCode*<br/>
Kod powiadomienia.

*Magazynie*<br/>
Identyfikator elementu menu, kontrolki lub akceleratora.

*hWndCtl*<br/>
Uchwyt do kontrolki okna.

*bHandled*<br/>
Mapa komunikatów ustawia *bHandled* na wartość true przed `CommandHandler` wywołaniem. Jeśli komunikat nie jest w `CommandHandler` pełni obsługiwany, należy ustawić *bHandled* na wartość false, aby wskazać, że komunikat musi zostać przetworzony.

## <a name="return-value"></a>Wartość zwracana

Wynik przetwarzania komunikatów. 0 w przypadku powodzenia.

## <a name="remarks"></a>Uwagi

Przykład użycia tego programu obsługi komunikatów w mapie komunikatów znajduje się w temacie [COMMAND_HANDLER](reference/message-map-macros-atl.md#command_handler).

## <a name="see-also"></a>Zobacz też

[Implementowanie okna](../atl/implementing-a-window.md)<br/>
[Mapy komunikatów](../atl/message-maps-atl.md)<br/>
[WM_NOTIFY](/windows/win32/controls/wm-notify)

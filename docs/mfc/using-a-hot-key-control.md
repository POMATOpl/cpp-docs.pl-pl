---
description: 'Dowiedz się więcej na temat: korzystanie z formantu klawisza dostępu'
title: Używanie formantu klawisza dostępu
ms.date: 11/04/2016
helpviewer_keywords:
- CHotKeyCtrl class [MFC], using
- hot key controls
ms.assetid: cdd6524b-cc43-447f-b151-164273559685
ms.openlocfilehash: 078cd4b3d4746723d5996959edad20dd44e9abec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202707"
---
# <a name="using-a-hot-key-control"></a>Używanie formantu klawisza dostępu

Typowy sposób użycia kontrolki klawisza skrótu jest następujący:

- Formant zostanie utworzony. Jeśli formant jest określony w szablonie okna dialogowego, tworzenie jest automatyczne po utworzeniu okna dialogowego. (W klasie okna dialogowego powinien znajdować się element [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md) , który odpowiada kontrolce klawisza skrótu). Alternatywnie możesz użyć funkcji [Utwórz](../mfc/reference/chotkeyctrl-class.md#create) element członkowski, aby utworzyć formant jako okno podrzędne dowolnego okna.

- Jeśli chcesz ustawić wartość domyślną dla kontrolki, wywołaj funkcję członkowską [SetHotKey](../mfc/reference/chotkeyctrl-class.md#sethotkey) . Jeśli chcesz zabronić niektórych stanów przesunięcia, wywołaj metodę [SetRules](../mfc/reference/chotkeyctrl-class.md#setrules). W przypadku kontrolek w oknie dialogowym dobry czas, który należy wykonać, jest w funkcji [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) okna dialogowego.

- Użytkownik współdziała z kontrolką, naciskając kombinację klawisza skrótu, gdy fokus jest aktywny. Następnie użytkownik może określić, że to zadanie zostało ukończone, na przykład przez kliknięcie przycisku w oknie dialogowym.

- Gdy program zostanie powiadomiony o tym, że użytkownik wybrał klawisz dostępu, powinien użyć funkcji elementu członkowskiego [GetHotKey](../mfc/reference/chotkeyctrl-class.md#gethotkey) do pobrania wartości klucza wirtualnego i zmiany stanu z formantu klawisza dostępu.

- Gdy wiesz, jaki klucz użytkownik zaznaczył, możesz ustawić klawisz dostępu przy użyciu jednej z metod opisanych w temacie [Ustawianie klawisza dostępu](../mfc/setting-a-hot-key.md).

- Jeśli kontrolka klawisza gorąca znajduje się w oknie dialogowym, a `CHotKeyCtrl` obiekt zostanie zniszczony automatycznie. Jeśli nie, musisz upewnić się, że zarówno kontrolka, jak i `CHotKeyCtrl` obiekt są prawidłowo niszczone.

## <a name="see-also"></a>Zobacz też

[Korzystanie z CHotKeyCtrl](../mfc/using-chotkeyctrl.md)<br/>
[Formanty](../mfc/controls-mfc.md)

---
description: 'Dowiedz się więcej na temat: Edytowanie etykiet kontrolki drzewa'
title: Edytowanie etykiety kontrolki drzewa
ms.date: 11/04/2016
helpviewer_keywords:
- editing tree control labels
- CTreeCtrl class [MFC], editing labels
- label editing in CTreeCtrl class [MFC]
- tree controls [MFC], label editing
ms.assetid: 6cde2ac3-43ee-468f-bac2-cf1a228ad32d
ms.openlocfilehash: b471b2ce9773ec86b1e4f94e766d3428fef456fa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264014"
---
# <a name="tree-control-label-editing"></a>Edytowanie etykiety kontrolki drzewa

Użytkownik może bezpośrednio edytować etykiety elementów w kontrolce drzewa ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)), która ma styl **TVS_EDITLABELS** . Użytkownik rozpoczyna edycję, klikając etykietę elementu, który ma fokus. Aplikacja rozpoczyna edytowanie przy użyciu funkcji składowej [EditLabel](../mfc/reference/ctreectrl-class.md#editlabel) . Formant drzewa wysyła powiadomienie po rozpoczęciu edycji i po jego anulowaniu lub zakończeniu. Po zakończeniu edycji użytkownik jest odpowiedzialny za aktualizowanie etykiety elementu, jeśli jest to konieczne.

Po rozpoczęciu edycji etykiet formant drzewa wysyła [TVN_BEGINLABELEDIT](/windows/win32/Controls/tvn-beginlabeledit) komunikat powiadomienia. Przetwarzając to powiadomienie, możesz zezwolić na edycję niektórych etykiet i uniemożliwić edytowanie innych. Zwrócenie wartości 0 pozwala na edycję i zwrócenie jej przez zero.

Gdy Edycja etykiet zostanie anulowana lub ukończona, kontrolka drzewa wyśle [TVN_ENDLABELEDIT](/windows/win32/Controls/tvn-endlabeledit) komunikat powiadomienia. Parametr *lParam* jest adresem struktury [NMTVDISPINFO](/windows/win32/api/commctrl/ns-commctrl-nmtvdispinfow) . **Element członkowski elementu** jest strukturą [TVITEM](/windows/win32/api/commctrl/ns-commctrl-tvitemw) , która identyfikuje element i zawiera edytowany tekst. Użytkownik jest odpowiedzialny za aktualizowanie etykiety elementu, jeśli jest to konieczne, ewentualnie po zweryfikowaniu edytowanego ciągu. Element członkowski *pszText* `TV_ITEM` ma wartość 0, jeśli edytowanie zostało anulowane.

Podczas edytowania etykiety, zazwyczaj w odpowiedzi na komunikat [TVN_BEGINLABELEDIT](/windows/win32/Controls/tvn-beginlabeledit) powiadomienia, można uzyskać wskaźnik do kontrolki edycji używanej do edycji etykiet przy użyciu funkcji składowej [GetEditControl](../mfc/reference/ctreectrl-class.md#geteditcontrol) . Można wywołać funkcję elementu członkowskiego [SetLimitText](../mfc/reference/cedit-class.md#setlimittext) kontrolki edycji, aby ograniczyć ilość tekstu, który użytkownik może wprowadzać lub podwoływać kontrolkę edycji w celu przechwycenia i odrzucenia nieprawidłowych znaków. Należy jednak pamiętać, że kontrolka edycji jest wyświetlana tylko *po* wysłaniu **TVN_BEGINLABELEDIT** .

## <a name="see-also"></a>Zobacz też

[Korzystanie z CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Formanty](../mfc/controls-mfc.md)

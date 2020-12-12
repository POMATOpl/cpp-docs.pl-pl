---
description: 'Dowiedz się więcej o: arkusze właściwości jako kreatory'
title: Arkusze właściwości jako kreatorzy
ms.date: 11/04/2016
helpviewer_keywords:
- property sheets, as wizards
ms.assetid: 1ea66ecb-23b0-484a-838d-58671a2999b5
ms.openlocfilehash: 2a68a16936e8ab134bab2fe78dac0d29c125b4db
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248869"
---
# <a name="property-sheets-as-wizards"></a>Arkusze właściwości jako kreatorzy

Kluczową cechą arkusza właściwości kreatora jest to, że nawigacja jest udostępniana za pomocą przycisków dalej lub Zakończ, wstecz i Anuluj zamiast tabulatorów. Przed wywołaniem metody [CPropertySheet::D omodal](../mfc/reference/cpropertysheet-class.md#domodal) w obiekcie arkusza właściwości należy wywołać metodę [CPropertySheet:: SetWizardMode](../mfc/reference/cpropertysheet-class.md#setwizardmode) .

Użytkownik otrzymuje te same [CPropertyPage:: OnSetActive](../mfc/reference/cpropertypage-class.md#onsetactive) i [CPropertyPage:: OnKillActive](../mfc/reference/cpropertypage-class.md#onkillactive) podczas przechodzenia z jednej strony na inną. Przyciski Dalej i Zakończ są wzajemnie wykluczające się kontrole; oznacza to, że w danym momencie będzie wyświetlana tylko jedna z nich. Na pierwszej stronie należy włączyć przycisk Dalej. Jeśli użytkownik znajduje się na ostatniej stronie, należy włączyć przycisk Zakończ. Nie jest to wykonywane automatycznie przez platformę. Musisz wywołać [CPropertySheet:: SetWizardButton](../mfc/reference/cpropertysheet-class.md#setwizardbuttons) na ostatniej stronie, aby to osiągnąć.

Aby wyświetlić wszystkie domyślne przyciski, mush Pokaż przycisk Zakończ i Przenieś przycisk Dalej. Następnie przenieś przycisk Wstecz, aby zachować jego względną pozycję do przycisku Dalej.

## <a name="example"></a>Przykład

[!code-cpp[NVC_MFCDocView#5](../mfc/codesnippet/cpp/property-sheets-as-wizards_1.cpp)]

## <a name="see-also"></a>Zobacz także

[Arkusze właściwości](../mfc/property-sheets-mfc.md)

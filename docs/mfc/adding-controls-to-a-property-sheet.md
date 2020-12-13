---
description: 'Dowiedz się więcej na temat: Dodawanie formantów do arkusza właściwości'
title: Dodawanie formantów do arkusza właściwości
ms.date: 11/04/2016
helpviewer_keywords:
- controls [MFC], adding to property sheets
- property sheets, adding controls
ms.assetid: 24ad4c0b-c1db-4850-b9f0-34aae8d74571
ms.openlocfilehash: e220d08b46f1db7e09ad1f1398731ce7a98f2dc5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339072"
---
# <a name="adding-controls-to-a-property-sheet"></a>Dodawanie formantów do arkusza właściwości

Domyślnie arkusz właściwości przydziela obszar okna dla stron właściwości, indeksu karty i przycisków OK, Anuluj i Zastosuj. (Niemodalny arkusz właściwości nie ma przycisków OK, Anuluj i Zastosuj). Możesz dodać inne kontrolki do arkusza właściwości. Na przykład można dodać okno podglądu z prawej strony obszaru Strona właściwości, aby pokazać użytkownikowi, jak będą wyglądać bieżące ustawienia w przypadku zastosowania do obiektu zewnętrznego.

Kontrolki można dodać do okna dialogowego arkusza właściwości w programie `OnCreate` obsługi. Obsługa dodatkowych kontrolek zwykle wymaga poszerzenia rozmiaru okna dialogowego arkusza właściwości. Po wywołaniu klasy bazowej **CPropertySheet:: OnCreate**, Call [GetWindowRect](reference/cwnd-class.md#getwindowrect) , aby uzyskać szerokość i wysokość okna aktualnie przydzielony arkusz właściwości, rozwiń wymiary prostokąta i Wywołaj [MoveWindow](reference/cwnd-class.md#movewindow) , aby zmienić rozmiar okna arkusza właściwości.

## <a name="see-also"></a>Zobacz też

[Arkusze właściwości](property-sheets-mfc.md)<br/>
[Klasa CPropertyPage](reference/cpropertypage-class.md)<br/>
[Klasa CPropertySheet](reference/cpropertysheet-class.md)

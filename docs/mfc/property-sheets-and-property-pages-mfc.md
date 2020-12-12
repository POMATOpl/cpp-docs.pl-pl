---
description: 'Dowiedz się więcej o: arkusze właściwości i strony właściwości (MFC)'
title: Arkusze właściwości i strony właściwości (MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], tabs
- property pages [MFC], property sheets
- CPropertyPage class [MFC], property sheets and pages
- CPropertySheet class [MFC], property sheets and pages
- property sheets, propert pages
ms.assetid: de8fea12-6c35-4cef-8625-b8073a379446
ms.openlocfilehash: 6819b890c699aeb428d2e0c76b048f5043e1dee7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248856"
---
# <a name="property-sheets-and-property-pages-mfc"></a>Arkusze właściwości i strony właściwości (MFC)

Okno [dialogowe](../mfc/dialog-boxes.md) MFC może podejmować instrukcje dotyczące wyświetlania kart właściwości i stron właściwości. "Arkusz właściwości" w MFC, ten rodzaj okna dialogowego, podobnie jak w przypadku wielu okien dialogowych w programach Microsoft Word, Excel i Visual C++, wygląda na to, że zawiera stos arkuszy z kartami, podobnie jak stos folderów plików widzianych od przodu do tyłu lub grupy okien kaskadowych. Kontrolki na karcie Front są widoczne; na kartach tylnych są widoczne tylko karty z etykietami. Arkusze właściwości są szczególnie przydatne do zarządzania dużą liczbą właściwości lub ustawień, które są dość starannie w kilku grupach. Zazwyczaj jeden arkusz właściwości może uprościć interfejs użytkownika, zastępując kilka oddzielnych okien dialogowych.

Począwszy od wersji 4,0 MFC, arkusze właściwości i strony właściwości są implementowane przy użyciu wspólnych formantów, które są dostarczane z systemami Windows 95 i Windows NT w wersji 3,51 i nowszych.

Arkusze właściwości są implementowane przy użyciu klas [CPropertySheet](../mfc/reference/cpropertysheet-class.md) i [CPropertyPage](../mfc/reference/cpropertypage-class.md) (opisanych w *dokumentacji MFC*). `CPropertySheet` definiuje ogólne okno dialogowe, które może zawierać wiele "stron" na podstawie `CPropertyPage` .

Aby uzyskać informacje na temat tworzenia i pracy z arkuszami właściwości, zobacz temat [arkusze właściwości](../mfc/property-sheets-mfc.md)tematu.

## <a name="see-also"></a>Zobacz też

[Okna dialogowe](../mfc/dialog-boxes.md)<br/>
[Praca z oknami dialogowymi w MFC](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[Arkusze właściwości i strony właściwości w MFC](../mfc/property-sheets-and-property-pages-in-mfc.md)<br/>
[Wymiana danych](../mfc/exchanging-data.md)<br/>
[Tworzenie niemodalnego arkusza właściwości](../mfc/creating-a-modeless-property-sheet.md)<br/>
[Obsługa przycisku Zastosuj](../mfc/handling-the-apply-button.md)

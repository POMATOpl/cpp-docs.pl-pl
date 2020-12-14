---
description: 'Dowiedz się więcej na temat: Dialog-Box składników w strukturze'
title: Składniki okna dialogowego w strukturze
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], creating
- dialog classes [MFC], dialog box components
- MFC dialog boxes [MFC], about MFC dialog boxes
- dialog templates [MFC], MFC framework
- MFC dialog boxes [MFC], dialog resource
ms.assetid: 592db160-0a8a-49be-ac72-ead278aca53f
ms.openlocfilehash: 406ffda122c6663d698f008a25164f8836221a2f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261544"
---
# <a name="dialog-box-components-in-the-framework"></a>Składniki okna dialogowego w strukturze

W strukturze MFC okno dialogowe ma dwa składniki:

- Zasób szablonu okna dialogowego, który określa kontrolki okna dialogowego i ich położenie.

   Zasób okna dialogowego przechowuje szablon okna dialogowego, z którego system Windows tworzy okno dialogowe i wyświetla je. Szablon określa charakterystyki okna dialogowego, w tym jego rozmiar, lokalizację, styl oraz typy i położenia kontrolek okna dialogowego. Zwykle używany jest szablon okna dialogowego przechowywany jako zasób, ale można również utworzyć własny szablon w pamięci.

- Klasa okna dialogowego, która pochodzi od [CDialog](reference/cdialog-class.md), aby zapewnić interfejs programistyczny do zarządzania oknem dialogowym.

   Okno dialogowe jest oknem i zostanie dołączone do okna systemu Windows, gdy będzie widoczne. Po utworzeniu okna dialogowego zasób szablonu okna dialogowego jest używany jako szablon do tworzenia kontrolek okna podrzędnego dla okna dialogowego.

## <a name="see-also"></a>Zobacz też

[Okna dialogowe](dialog-boxes.md)<br/>
[Praca z oknami dialogowymi w MFC](life-cycle-of-a-dialog-box.md)

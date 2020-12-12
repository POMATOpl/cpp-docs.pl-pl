---
description: 'Dowiedz się więcej na temat: Tworzenie modalnych okien dialogowych'
title: Tworzenie modalnych okien dialogowych
ms.date: 11/04/2016
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], modal
ms.assetid: 26c7a68c-79f6-4862-a5a8-6024984644d2
ms.openlocfilehash: 82fa10c65161df98ea3d377e302c0fb787feb14c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309800"
---
# <a name="creating-modal-dialog-boxes"></a>Tworzenie modalnych okien dialogowych

Aby utworzyć modalne okno dialogowe, wywołaj jeden z dwóch publicznych konstruktorów zadeklarowanych w [CDialog](reference/cdialog-class.md). Następnie wywołaj funkcję elementu członkowskiego [DoModal](reference/cdialog-class.md#domodal) obiektu okna dialogowego, aby wyświetlić okno dialogowe i zarządzać interakcją z nim, dopóki użytkownik nie wybierze przycisku OK lub anuluje. To zarządzanie przez `DoModal` to, co sprawia, że okno dialogowe jest modalne. W przypadku modalnych okien dialogowych `DoModal` wczytuje zasób okna dialogowego.

## <a name="see-also"></a>Zobacz też

[Praca z oknami dialogowymi w MFC](life-cycle-of-a-dialog-box.md)

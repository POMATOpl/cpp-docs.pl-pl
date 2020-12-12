---
description: 'Dowiedz się więcej na temat: Tworzenie niemodalnych okien dialogowych'
title: Tworzenie niemodalnych okien dialogowych
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
ms.assetid: 70d78c7f-3d40-477b-9f78-0f33c359f88b
ms.openlocfilehash: c754391a0f1ab2713f3ce01b5d30ccc33be4aaa5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309787"
---
# <a name="creating-modeless-dialog-boxes"></a>Tworzenie niemodalnych okien dialogowych

W przypadku niemodalnego okna dialogowego musisz podać własny Konstruktor publiczny w swojej klasie okna dialogowego. Aby utworzyć niemodalne okno dialogowe, Wywołaj konstruktora publicznego, a następnie wywołaj funkcję [tworzenia](reference/cdialog-class.md#create) członka obiektu okna dialogowego w celu załadowania zasobu okna dialogowego. Można wywołać metodę **Create** w trakcie lub po wywołaniu konstruktora. Jeśli zasób okna dialogowego ma właściwość **WS_VISIBLE**, zostanie wyświetlone okno dialogowe. W przeciwnym razie należy wywołać funkcję członkowską [Funkcja ShowWindow](reference/cwnd-class.md#showwindow) .

## <a name="see-also"></a>Zobacz też

[Praca z oknami dialogowymi w MFC](life-cycle-of-a-dialog-box.md)

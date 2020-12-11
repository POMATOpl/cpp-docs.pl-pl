---
description: 'Dowiedz się więcej na temat: używanie niestandardowych ciągów formatu w kontrolce selektora dat i godzin'
title: Używanie niestandardowych ciągów formatu w formancie selektora dat i godzin
ms.date: 11/04/2016
helpviewer_keywords:
- CDateTimeCtrl class [MFC], display styles
- DateTimePicker control [MFC], display styles
- DateTimePicker control [MFC]
ms.assetid: 7d577f03-6ca0-4597-9093-50b78f304719
ms.openlocfilehash: 91add199ffd852a107588617d47a2fd51136596d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154555"
---
# <a name="using-custom-format-strings-in-a-date-and-time-picker-control"></a>Używanie niestandardowych ciągów formatu w formancie selektora dat i godzin

Domyślnie kontrolki selektora daty i godziny zapewniają trzy typy formatu (każdy format odpowiadający unikatowemu stylowi) do wyświetlania bieżącej daty lub godziny:

- **DTS_LONGDATEFORMAT** Wyświetla datę w długim formacie, generując dane wyjściowe, takie jak "Środa, 3 stycznia 2000".

- **DTS_SHORTDATEFORMAT** Wyświetla datę w krótkim formacie, generując dane wyjściowe, takie jak "1/3/00".

- **DTS_TIMEFORMAT** Wyświetla godzinę w formacie długim, generując dane wyjściowe, takie jak "5:31:42 PM".

Można jednak dostosować wygląd daty lub godziny przy użyciu ciągu formatu niestandardowego. Ten ciąg niestandardowy składa się z istniejących znaków formatowania, znaków niesformatowanych lub kombinacji obu. Po skompilowaniu niestandardowego ciągu, należy wywołać metodę [Korzystanie CDateTimeCtrl:: SetFormat](../mfc/reference/cdatetimectrl-class.md#setformat) przekazującą w niestandardowym ciągu. W kontrolce selektora daty i godziny zostanie wyświetlona bieżąca wartość przy użyciu ciągu formatu niestandardowego.

Poniższy przykładowy kod (gdzie *m_dtPicker* jest `CDateTimeCtrl` obiekt) ilustruje jedno z możliwych rozwiązań:

[!code-cpp[NVC_MFCControlLadenDialog#7](../mfc/codesnippet/cpp/using-custom-format-strings-in-a-date-and-time-picker-control_1.cpp)]

Oprócz niestandardowych ciągów formatu, kontrolki selektora daty i godziny obsługują również [pola wywołania zwrotnego](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md).

## <a name="see-also"></a>Zobacz też

[Korzystanie z CDateTimeCtrl](../mfc/using-cdatetimectrl.md)<br/>
[Formanty](../mfc/controls-mfc.md)

---
description: 'Dowiedz się więcej o: implementacja paska stanu w MFC'
title: Implementacja paska stanu w MFC
ms.date: 11/19/2018
f1_keywords:
- COldStatusBar
helpviewer_keywords:
- status bars [MFC], implementing in MFC
- CStatusBarCtrl class [MFC], and MFC status bars
- CStatusBar class [MFC], and CStatusBarCtrl class [MFC]
- CStatusBarCtrl class [MFC], and CStatusBar class [MFC]
- status bars [MFC], backward compatibility
- status bars [MFC], old with COldStatusBar class [MFC]
- COldStatusBar class [MFC]
- status bars [MFC], and CStatusBarCtrl class
- CStatusBar class [MFC], and MFC status bars
- status indicators
- status bars [MFC], Windows 95 implementation
ms.assetid: be5cd876-38e3-4d5c-b8cb-16d57a16a142
ms.openlocfilehash: d42f8b4bf6ae72cf8eb4a12d1f5eafb8603c5e1b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216759"
---
# <a name="status-bar-implementation-in-mfc"></a>Implementacja paska stanu w MFC

Obiekt [CStatusBar](../mfc/reference/cstatusbar-class.md) jest paskiem sterowania z wierszem okienka tekstu wyjściowego. Okienka danych wyjściowych są często używane jako wiersze komunikatów i jako wskaźniki stanu. Przykłady obejmują menu Pomoc — wiersze komunikatów, które krótko objaśniają wybrane polecenie menu i wskaźniki pokazujące stan blokady przewijania, NUM LOCK i innych kluczy.

Począwszy od wersji 4,0, paski stanu są implementowane przy użyciu klasy [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md), która hermetyzuje wspólny formant paska stanu. W celu zapewnienia zgodności z poprzednimi wersjami MFC zachowuje starszą implementację paska stanu w klasie `COldStatusBar` . Dokumentacja dotycząca wcześniejszych wersji MFC została zamieszczona `COldStatusBar` w temacie `CStatusBar` .

[CStatusBar:: GetStatusBarCtrl](../mfc/reference/cstatusbar-class.md#getstatusbarctrl), funkcja członkowska New to MFC 4,0, umożliwia korzystanie z pomocy technicznej programu Windows Common Control do dostosowywania paska stanu i dodatkowych funkcji. `CStatusBar` funkcje składowe zapewniają większość funkcji formantów standardowych systemu Windows; Jednak po wywołaniu programu `GetStatusBarCtrl` można dać paski stanu jeszcze większą charakterystykę paska stanu. Po wywołaniu `GetStatusBarCtrl` , zwróci odwołanie do `CStatusBarCtrl` obiektu. Za pomocą tego odwołania można manipulować formantem paska stanu.

Na poniższej ilustracji przedstawiono pasek stanu, w którym wyświetlane są różne wskaźniki.

![Pasek stanu](../mfc/media/vc37dy1.gif "Pasek stanu") <br/>
Pasek stanu

Podobnie jak w przypadku paska narzędzi, obiekt pasek stanu jest osadzony w oknie ramki nadrzędnej i jest tworzony automatycznie podczas konstruowania okna ramki. Pasek stanu, podobnie jak wszystkie paski kontroli, jest niszczony automatycznie, gdy ramka nadrzędna zostanie zniszczona.

## <a name="what-do-you-want-to-know-more-about"></a>Co chcesz dowiedzieć się więcej o

- [Aktualizowanie tekstu w okienku paska stanu](../mfc/updating-the-text-of-a-status-bar-pane.md)

- Klasy MFC [CStatusBar](../mfc/reference/cstatusbar-class.md) i [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)

- [Paski sterowania](../mfc/control-bars.md)

- [Paski dialogowe](../mfc/dialog-bars.md)

- [Paski narzędzi (implementacja paska narzędzi MFC)](../mfc/mfc-toolbar-implementation.md)

## <a name="see-also"></a>Zobacz też

[Paski stanu](../mfc/status-bars.md)

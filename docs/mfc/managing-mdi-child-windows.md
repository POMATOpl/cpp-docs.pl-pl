---
description: Dowiedz się więcej na temat zarządzania oknami podrzędnymi MDI
title: Zarządzanie oknami podrzędnymi MDI
ms.date: 11/19/2018
f1_keywords:
- MDICLIENT
helpviewer_keywords:
- MDI [MFC], child windows
- child windows [MFC], and MDICLIENT window
- MDICLIENT window [MFC]
- windows [MFC], MDI
- frame windows [MFC], MDI child windows
- child windows [MFC]
- MDI [MFC], frame windows
ms.assetid: 1828d96e-a561-48ae-a661-ba9701de6bee
ms.openlocfilehash: 1207e6a8fa174c36b09352796521bcb860ee665f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97112092"
---
# <a name="managing-mdi-child-windows"></a>Zarządzanie oknami podrzędnymi MDI

Główne ramki interfejsu MDI (jeden na aplikację) zawierają specjalne okno podrzędne o nazwie okno MDICLIENT. Okno MDICLIENT zarządza obszarem klienckim okna głównej ramki, a sama sama ma okna podrzędne: okna dokumentów pochodne `CMDIChildWnd` . Ponieważ okna dokumentów są samymi oknami ramek (podrzędnymi oknami MDI), mogą również mieć własne elementy podrzędne. We wszystkich tych przypadkach okno nadrzędne zarządza jego podrzędnymi oknami i przekazuje je do nich.

W oknie ramka MDI okno ramka zarządza oknem MDICLIENT, umieszczając je w połączeniu z paskami sterowania. Okno MDICLIENT, z kolei, zarządza wszystkimi oknami podrzędnymi ramek MDI. Poniższy rysunek przedstawia relację między oknem ramki MDI, oknem MDICLIENT i jego podrzędnymi oknami ramek dokumentu.

![Okna podrzędne w oknie ramka MDI](../mfc/media/vc37gb1.gif "Okna podrzędne w oknie ramka MDI") <br/>
Okna ramek MDI i elementy podrzędne

Okno ramki MDI działa również w połączeniu z bieżącym oknem podrzędnym MDI, jeśli istnieje. Okno ramka MDI deleguje komunikaty poleceń do elementu podrzędnego MDI, zanim spróbuje je obsłużyć.

## <a name="what-do-you-want-to-know-more-about"></a>Co chcesz dowiedzieć się więcej o

- [Tworzenie okien ramowych dokumentu](creating-document-frame-windows.md)

- [Style okna ramowego](frame-window-styles-cpp.md)

## <a name="see-also"></a>Zobacz też

[Korzystanie z okien ramowych](using-frame-windows.md)

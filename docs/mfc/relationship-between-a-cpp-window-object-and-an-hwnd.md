---
description: 'Dowiedz się więcej na temat: relacja między obiektem okna języka C++ a elementem HWND'
title: Relacja między obiektem okna języka C++ a właściwością HWND
ms.date: 11/19/2018
f1_keywords:
- HWND
helpviewer_keywords:
- Windows window [MFC]
- window objects [MFC], HWND and
- HWND [MFC]
- CWnd class [MFC], HWND
- HWND, window objects [MFC]
ms.assetid: f2e76340-6691-4ee6-9424-0345634a9469
ms.openlocfilehash: bdcf52d2890265b854e3eef7854b489b47eda6a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218098"
---
# <a name="relationship-between-a-c-window-object-and-an-hwnd"></a>Relacja między obiektem okna języka C++ a właściwością HWND

*Obiekt* Window jest obiektem klasy języka C++ `CWnd` (lub klasy pochodnej), którą program tworzy bezpośrednio. Jest on dostępny i pojawia się w odpowiedzi na wywołania konstruktora i destruktora programu. *Okno* systemu Windows, z drugiej strony, to nieprzezroczyste dojście do wewnętrznej struktury danych systemu Windows, które odnosi się do okna i zużywa zasoby systemowe, gdy są obecne. Okno systemu Windows jest identyfikowane przez "uchwyt okna" ( `HWND` ) i jest tworzone po `CWnd` utworzeniu obiektu przez wywołanie do `Create` funkcji składowej klasy `CWnd` . Okno może zostać zniszczone przez wywołanie programu lub akcję użytkownika. Uchwyt okna jest przechowywany w zmiennej składowej *m_hWnd* obiektu okna. Poniższy rysunek przedstawia relację między obiektem okna języka C++ a oknem systemu Windows. Tworzenie okien jest omówione w temacie [Tworzenie systemu Windows](../mfc/creating-windows.md). Niszczenie okien jest omówione w przypadku [niszczenia obiektów okien](../mfc/destroying-window-objects.md).

![Obiekt okna CWnd i okno wyników](../mfc/media/vc37fj1.gif "Obiekt okna CWnd i okno wyników") <br/>
Okno obiektu okna i okna systemu Windows

## <a name="see-also"></a>Zobacz też

[Obiekty okna](../mfc/window-objects.md)

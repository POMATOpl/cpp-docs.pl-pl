---
description: 'Dowiedz się więcej o programie: obiekty okna'
title: Obiekty okien
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], window
- Windows window [MFC]
- MFC, windows
- frame windows [MFC], C++ window objects
- window objects [MFC]
- windows [MFC], C++ window objects
- window messages [MFC]
- HWND
- messages [MFC], Windows
- Visual C++, window objects [MFC]
- HWND, window objects [MFC]
ms.assetid: 28b33ce2-af05-4617-9d03-1cb9a02be687
ms.openlocfilehash: 5a7755dfecc8205279785a6452b04c3f8dc429d1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214497"
---
# <a name="window-objects"></a>Obiekty okien

MFC dostarcza klasy [CWnd](../mfc/reference/cwnd-class.md) do hermetyzacji `HWND` uchwytu okna. `CWnd`Obiekt jest obiektem okna języka C++, odrębnie od `HWND` reprezentowanego okna systemu Windows, ale go zawiera. Użyj `CWnd` , aby utworzyć własne klasy okien podrzędnych lub użyć jednej z wielu klas MFC pochodnych z `CWnd` . Klasa `CWnd` jest klasą bazową dla wszystkich okien, w tym okna z ramkami, okna dialogowe, okna podrzędne, kontrolki i paski formantów, takie jak paski narzędzi. Dobre zrozumienie [relacji między obiektem okna języka C++ a elementem HWND](../mfc/relationship-between-a-cpp-window-object-and-an-hwnd.md) ma kluczowe znaczenie dla efektywnego programowania za pomocą MFC.

MFC zapewnia pewne domyślne funkcje i zarządzanie systemem Windows, ale można utworzyć własną klasę z `CWnd` i użyć jej funkcji składowych, aby dostosować dostępne funkcje. Można utworzyć okna podrzędne poprzez konstruowanie `CWnd` obiektu i wywołanie jego funkcji [tworzenia](../mfc/reference/cwnd-class.md#create) elementu członkowskiego, a następnie dostosowanie okien podrzędnych przy użyciu `CWnd` funkcji składowych. Można osadzić obiekty pochodne od [CView](../mfc/reference/cview-class.md), takie jak widoki formularzy lub widoki drzewa, w oknie ramek. I można obsługiwać wiele widoków dokumentów za pośrednictwem okienek rozdzielacza dostarczonych przez klasę [CSplitterWnd](../mfc/reference/csplitterwnd-class.md).

Każdy obiekt pochodny klasy `CWnd` zawiera mapę komunikatów, za pomocą której można mapować komunikaty systemu Windows lub identyfikatory poleceń na własne programy obsługi.

Ogólna literatura dotycząca programowania dla systemu Windows to dobry zasób do uczenia się, jak używać `CWnd` funkcji Członkowskich, które hermetyzują `HWND` interfejsy API.

## <a name="functions-for-operating-on-a-cwnd"></a>Funkcje do działania na CWnd

`CWnd` natomiast [klasy pochodnego okna](../mfc/derived-window-classes.md) zapewniają konstruktory, destruktory i funkcje członkowskie do inicjowania obiektu, tworzenia podstawowych struktur systemu Windows i uzyskiwania dostępu do hermetyzacji `HWND` . `CWnd` Program udostępnia również funkcje członkowskie, które hermetyzują interfejsy API systemu Windows do wysyłania wiadomości, uzyskiwania dostępu do stanu okna, konwertowania współrzędnych, aktualizowania, przewijania, uzyskiwania dostępu do schowka i wielu innych zadań. Większość interfejsów API zarządzania oknami systemu Windows, które przyjmują `HWND` argument, są hermetyzowane jako funkcje elementów członkowskich programu `CWnd` . Nazwy funkcji i ich parametrów są zachowywane w `CWnd` funkcji składowej. Aby uzyskać szczegółowe informacje o interfejsach API systemu Windows, które są hermetyzowane przez `CWnd` program, zobacz Klasa [CWnd](../mfc/reference/cwnd-class.md).

## <a name="cwnd-and-windows-messages"></a>CWnd i komunikaty systemu Windows

Jednym z podstawowych celów `CWnd` jest zapewnienie interfejsu do obsługi komunikatów systemu Windows, takich jak WM_PAINT lub WM_MOUSEMOVE. Wiele funkcji składowych programu `CWnd` jest obsługą dla standardowych komunikatów — zaczynają się od identyfikatora **afx_msg** i prefiksu "on", takich jak `OnPaint` i `OnMouseMove` . [Obsługa komunikatów i mapowanie](../mfc/message-handling-and-mapping.md) obejmują szczegóły komunikatów i komunikatów. Informacje dotyczą zarówno systemu Windows Framework, jak i tych, które zostały utworzone w celach specjalnych.

### <a name="what-do-you-want-to-know-more-about"></a>Co chcesz dowiedzieć się więcej o

- [Relacja między obiektem okna języka C++ a elementem HWND](../mfc/relationship-between-a-cpp-window-object-and-an-hwnd.md)

- [Pochodne klasy okien](../mfc/derived-window-classes.md)

- [Tworzenie okien](../mfc/creating-windows.md)

- [niszczenie obiektów okien](../mfc/destroying-window-objects.md)

- [Odłączanie elementu CWnd od jego elementu HWND](../mfc/detaching-a-cwnd-from-its-hwnd.md)

- [Praca z obiektami okien](../mfc/working-with-window-objects.md)

- [Konteksty urządzenia](../mfc/device-contexts.md): obiekty, które tworzą niezależne urządzenie do rysowania systemu Windows

- [Obiekty graficzne](../mfc/graphic-objects.md): pióra, pędzle, czcionki, mapy bitowe, palety, regiony

## <a name="see-also"></a>Zobacz też

[Windows](../mfc/windows.md)

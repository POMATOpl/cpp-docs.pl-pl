---
description: 'Dowiedz się więcej na temat: rejestrowanie klas okien'
title: Rejestrowanie klas okien
ms.date: 11/04/2016
f1_keywords:
- WndProc
helpviewer_keywords:
- window classes [MFC], registering
- registry [MFC], registering classes
- AfxRegisterWndClass method [MFC]
- MFC, windows
- WinMain method [MFC], and registering window classes
- WndProc method [MFC]
- classes [MFC], registering window classes
- WinMain method [MFC]
- registering window classes [MFC]
ms.assetid: 30994bc4-a362-43da-bcc5-1bf67a3fc929
ms.openlocfilehash: e31f83b691ad12d845afca6a3a5f18d9ba64b0e6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218195"
---
# <a name="registering-window-classes"></a>Rejestrowanie klas okien

Okno "klasy" w tradycyjnym programowaniu dla systemu Windows definiują charakterystykę "Class" (nie klasę C++), z której można utworzyć dowolną liczbę okien. Ten rodzaj klasy jest szablonem lub modelem do tworzenia systemu Windows.

## <a name="window-class-registration-in-traditional-programs-for-windows"></a>Rejestracja klasy okna w tradycyjnych programach dla systemu Windows

W tradycyjnym programie dla systemu Windows, bez MFC, przetwarzasz wszystkie komunikaty do okna w jego "procedurze okna" lub " `WndProc` ." A `WndProc` jest skojarzony z oknem przy użyciu procesu "Rejestracja klasy okna". Okno główne jest zarejestrowane w `WinMain` funkcji, ale inne klasy systemu Windows mogą być rejestrowane w dowolnym miejscu aplikacji. Rejestracja zależy od struktury, która zawiera wskaźnik do `WndProc` funkcji, wraz ze specyfikacjami kursora, pędzlem tła itd. Struktura jest przenoszona jako parametr, wraz z nazwą ciągu klasy, we wcześniejszej wywołaniu `RegisterClass` funkcji. W ten sposób Klasa rejestracji może być współużytkowana przez wiele okien.

## <a name="window-class-registration-in-mfc-programs"></a>Rejestracja klasy okna w programach MFC

Z kolei większość działań rejestracji klasy okna jest wykonywana automatycznie w programie MFC Framework. Jeśli używasz MFC, zazwyczaj uzyskujesz klasę okna języka C++ z istniejącej klasy biblioteki przy użyciu standardowej składni języka C++ do dziedziczenia klas. Struktura nadal używa tradycyjnych "klas rejestracji" i udostępnia kilka standardowych, które są zarejestrowane w razie potrzeby. Można zarejestrować dodatkowe klasy rejestracji przez wywołanie funkcji globalnej [AfxRegisterWndClass —](../mfc/reference/application-information-and-management.md#afxregisterwndclass) , a następnie przekazanie zarejestrowanej klasy do `Create` funkcji członkowskiej `CWnd` . Zgodnie z opisem w tym miejscu tradycyjna "Klasa rejestracji" w systemie Windows nie należy mylić z klasą języka C++.

Aby uzyskać więcej informacji, zobacz [Uwaga techniczna 1](../mfc/tn001-window-class-registration.md).

## <a name="see-also"></a>Zobacz też

[Tworzenie okien](../mfc/creating-windows.md)

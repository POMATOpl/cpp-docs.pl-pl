---
description: 'Dowiedz się więcej o: modyfikowanie kontrolki DHTML ATL'
title: Modyfikowanie kontrolki DHTML ATL
ms.date: 11/04/2016
helpviewer_keywords:
- HTML controls, modifying
- DHTML controls
- DHTML controls, modifying
ms.assetid: c053f35f-8629-4600-9595-721f5956777a
ms.openlocfilehash: 7ae9c102addd7a33341a8f16105a3581de10481e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159456"
---
# <a name="modifying-the-atl-dhtml-control"></a>Modyfikowanie kontrolki DHTML ATL

Kreator kontrolki ATL udostępnia kod początkowy, dzięki czemu można kompilować i uruchamiać kontrolkę, aby zobaczyć, jak metody są zapisywane w plikach projektu i jak kod DHTML wywołuje w kodzie C++ formantu przy użyciu metod wysyłania. Do interfejsu można dodać dowolną metodę wysyłania. Następnie można wywołać metody z zasobu HTML.

## <a name="to-modify-the-atl-dhtml-control"></a>Aby zmodyfikować formant ATL DHTML

1. W **Widok klasy** rozwiń projekt kontrolki.

   Należy zauważyć, że interfejs kończący się znakiem "UI" ma jedną metodę `OnClick` . Interfejs, który nie kończy się na "interfejsie użytkownika" nie ma żadnych metod.

1. Dodaj metodę o nazwie `MethodInvoked` do interfejsu, który nie kończy się "interfejsem użytkownika".

   Ta metoda zostanie dodana do interfejsu, który jest używany w kontenerze sterowania dla interakcji kontenera, a nie do interfejsu używanego przez DHTML do interakcji z kontrolką. Tylko kontener może wywołać tę metodę.

1. Znajdź metodę użyto metod zastępczych w pliku. cpp i Dodaj kod, aby wyświetlić okno komunikatu, na przykład:

   [!code-cpp[NVC_ATL_COM#5](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_1.cpp)]

1. Dodaj inną metodę o nazwie `HelloHTML` , tylko ten czas, Dodaj ją do interfejsu kończącego się na "interfejsie użytkownika". Znajdź `HelloHTML` metodę użyto metod zastępczych w pliku. cpp i Dodaj kod, aby wyświetlić okno komunikatu, na przykład:

   [!code-cpp[NVC_ATL_COM#6](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_2.cpp)]

1. Dodaj trzecią metodę, `GoToURL` do interfejsu, który nie kończy się "interfejsem użytkownika". Zaimplementuj tę metodę przez wywołanie [IWebBrowser2:: Nawiguj](/previous-versions//aa752133\(v=vs.85\))w następujący sposób:

   [!code-cpp[NVC_ATL_COM#7](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_3.cpp)]

   Możesz użyć metod, `IWebBrowser2` ponieważ ATL udostępnia wskaźnik do tego interfejsu w pliku h.

Następnie zmodyfikuj zasób HTML w celu wywołania utworzonych metod. Do wywoływania tych metod zostaną dodane trzy przyciski.

## <a name="to-modify-the-html-resource"></a>Aby zmodyfikować zasób HTML

1. W **Eksplorator rozwiązań** kliknij dwukrotnie plik. htm, aby wyświetlić zasób html.

   Przejrzyj kod HTML, szczególnie wywołania zewnętrznych metod wysyłania systemu Windows. KOD HTML wywołuje `OnClick` metodę projektu, a parametry wskazują treść formantu ( `theBody` ) i kolor do przypisania (" `red` "). Tekst następujący po wywołaniu metody jest etykietą, która pojawia się na przycisku.

1. Dodaj kolejną `OnClick` metodę, tylko Zmień kolor. Na przykład:

    ```html
    <br>
    <br>
    <BUTTON onclick='window.external.OnClick(theBody, "white");'>Refresh</BUTTON>
    ```

   Ta metoda spowoduje utworzenie przycisku z etykietą **Odśwież**, który użytkownik może kliknąć, aby przywrócić formant do oryginalnego, białego tła.

1. Dodaj wywołanie do `HelloHTML` metody, która została utworzona. Na przykład:

    ```html
    <br>
    <br>
    <BUTTON onclick='window.external.HelloHTML();'>HelloHTML</BUTTON>
    ```

   Ta metoda utworzy przycisk o nazwie **HelloHTML**, który użytkownik może kliknąć, aby wyświetlić `HelloHTML` okno komunikatu.

Teraz można skompilować i [przetestować zmodyfikowaną kontrolkę DHTML](../atl/testing-the-modified-atl-dhtml-control.md).

## <a name="see-also"></a>Zobacz też

[Obsługa formantów DHTML](../atl/atl-support-for-dhtml-controls.md)

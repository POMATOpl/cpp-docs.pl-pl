---
description: 'Dowiedz się więcej o: testowanie zmodyfikowanej kontrolki DHTML ATL'
title: Testowanie zmodyfikowanej kontrolki DHTML ATL
ms.date: 11/06/2018
helpviewer_keywords:
- HTML controls, testing
- testing controls
- DHTML controls, testing
ms.assetid: 42316118-9433-410f-9d8a-0efcc1eff824
ms.openlocfilehash: a797eab308ad7fb8c5c7b72566ec3d57a169370b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138336"
---
# <a name="testing-the-modified-atl-dhtml-control"></a>Testowanie zmodyfikowanej kontrolki DHTML ATL

Wypróbuj nową kontrolkę, aby zobaczyć, jak działa teraz.

## <a name="to-build-and-test-the-modified-control"></a>Aby skompilować i przetestować zmodyfikowaną kontrolkę

1. Skompiluj ponownie projekt i otwórz go w **kontenerze testów**. Zobacz [testowanie właściwości i zdarzeń za pomocą kontenera testów,](../mfc/testing-properties-and-events-with-test-container.md) Aby uzyskać informacje na temat uzyskiwania dostępu do **kontenera testowego**.

   Zmień rozmiar kontrolki, aby wyświetlić wszystkie dodane przyciski.

1. Przejrzyj dwa przyciski, które zostały wstawione przez zmianę kodu HTML. Każdy przycisk nosi etykietę zidentyfikowaną podczas [modyfikowania kontrolki DHTML ATL](../atl/modifying-the-atl-dhtml-control.md): **Refresh** i **HelloHTML**.

1. Przetestuj dwa nowe przyciski, aby zobaczyć, jak działają.

Teraz Przetestuj metody, które nie są częścią interfejsu użytkownika.

1. Zaznacz kontrolkę, aby uaktywnić obramowanie.

1. W menu **sterowania** wybierz polecenie **wywołaj metody**.

   Metody z listy z etykietą **Nazwa metody** są metodami, które mogą być wywoływane przez kontener: `MethodInvoked` i `GoToURL` . Wszystkie inne metody są kontrolowane przez interfejs użytkownika.

1. Wybierz metodę do wywołania i wybierz polecenie **Invoke** , aby wyświetlić okno komunikatu metody lub przejdź do `www.microsoft.com` .

1. W oknie dialogowym **wywoływanie metod** wybierz pozycję **Zamknij**.

Aby dowiedzieć się więcej na temat różnych elementów i plików, które składają się na formant ATL DHTML, zobacz [Identyfikowanie elementów projektu kontrolki DHTML](../atl/identifying-the-elements-of-the-dhtml-control-project.md).

## <a name="see-also"></a>Zobacz też

[Obsługa formantów DHTML](../atl/atl-support-for-dhtml-controls.md)

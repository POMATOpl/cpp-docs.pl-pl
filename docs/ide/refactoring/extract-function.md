---
description: 'Dowiedz się więcej na temat: Extract — Funkcja'
title: Extract — Funkcja
ms.date: 11/16/2016
ms.assetid: e31d1249-9705-4511-acbd-9f6fe73bdf2d
ms.openlocfilehash: 4ae5e858c658d14e72db8740232b74935c655292
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259763"
---
# <a name="extract-function"></a>Extract — Funkcja

**Co:** Umożliwia włączenie fragmentu kodu do jego własnej funkcji.

**Kiedy:** Istnieje fragment istniejącego kodu w niektórych funkcjach, które muszą być wywoływane z innej funkcji.

**Dlaczego:** Można skopiować/wkleić ten kod, ale może to prowadzić do duplikacji.  Lepszym rozwiązaniem jest Refaktoryzacja tego fragmentu do własnej funkcji, która może być wywoływana swobodnie przez jakąkolwiek inną funkcję.

**Jaka**

1. Zaznacz kod, który ma zostać wyodrębniony:

   ![Wyróżniony kod](images/extractfunction_highlight.png)

1. Następnie wykonaj jedną z następujących czynności:
   * **Klawiatura**
     * Naciśnij klawisze **Ctrl + R**, a następnie **Ctrl + M**.  (Pamiętaj, że skrót klawiaturowy może się różnić w zależności od wybranego profilu).
     * Naciśnij **klawisze CTRL +.** Aby wyzwolić menu **szybkie akcje i refaktoryzacje** , a następnie wybierz pozycję **Wyodrębnij funkcję (eksperymentalne)** z menu kontekstowego.
   * **Mysz**
     * Wybierz pozycję **edytuj > refaktoryzacja > Wyodrębnij funkcję (eksperymentalne)**.
     * Kliknij prawym przyciskiem myszy kod, wybierz menu **szybkie akcje i refaktoryzacje** i wybierz polecenie **Wyodrębnij funkcję (eksperymentalne)** z menu kontekstowego.
     * Kliknij ![ ikonę żarówki, ](images/bulb.png) która pojawia się na lewym marginesie, a następnie wybierz pozycję **Wyodrębnij funkcję (eksperymentalne)** z menu kontekstowego.

1. W oknie **Wyodrębnij funkcję/metodę (eksperymentalne)** wprowadź nową nazwę funkcji, wybierz miejsce, w którym ma zostać umieszczony kod, a następnie kliknij przycisk **OK** .

   ![Okno dialogowe wyodrębniania funkcji](images/extractfunction_dialog.png)

1. Nowa funkcja zostanie utworzona, gdy zostanie określony, prototyp funkcji w odpowiednim pliku nagłówkowym, a oryginalny kod zostanie zmieniony w celu wywołania tej funkcji.

   ![Wyodrębnij wynik funkcji](images/extractfunction_result.png)

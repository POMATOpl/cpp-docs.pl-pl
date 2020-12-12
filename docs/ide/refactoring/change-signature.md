---
description: 'Dowiedz się więcej na temat: Zmień sygnaturę'
title: Zmień sygnaturę
ms.date: 11/16/2016
ms.assetid: 8daaa060-7305-4035-99d2-8b460b4f4454
ms.openlocfilehash: 2530a13f3e0e4a1aad987a4eed9dfc49b91323de
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185690"
---
# <a name="change-signature"></a>Zmień sygnaturę

**Co:** Umożliwia modyfikowanie parametrów funkcji.

**Kiedy:** Należy zmienić kolejność, dodać, usunąć lub zmodyfikować parametry funkcji, które są obecnie używane w różnych lokalizacjach.

**Dlaczego:** Możesz ręcznie zmienić te parametry, a następnie znaleźć wszystkie wywołania tej funkcji i zmienić je jeden do jednego, ale może to prowadzić do błędów.  To narzędzie refaktoryzacji wykona zadanie automatycznie.

**Jaka**

1. Umieść kursor tekstowy lub mysz wewnątrz nazwy metody do zmodyfikowania lub jednego z jej użycia:

   ![Wyróżniony kod](images/changesignature_highlight.png)

1. Następnie wykonaj jedną z następujących czynności:
   * **Klawiatura**
     * Naciśnij klawisze **Ctrl + R**, a następnie **Ctrl + O**.  (Pamiętaj, że skrót klawiaturowy może się różnić w zależności od wybranego profilu).
     * Naciśnij **klawisze CTRL +.** Aby wyzwolić menu **szybkie akcje i refabryki** , a następnie wybierz pozycję **Zmień sygnaturę** z menu kontekstowego.
   * **Mysz**
     * Wybierz pozycję **edytuj > refaktoryzacja > Zmień kolejność parametrów**.
     * Kliknij prawym przyciskiem myszy kod, wybierz menu **szybkie akcje i refaktoryzacje** i wybierz polecenie **Zmień sygnaturę** z menu kontekstowego.

1. W oknie dialogowym **Zmienianie podpisu** , które się pojawia, możesz użyć przycisków z prawej strony, aby zmienić sygnaturę metody:

   ![Okno dialogowe Zmienianie sygnatury](images/changesignature_dialog.png)

   | Przycisk | Opis
   | ------ | ---
   | **W górę/w dół**    | Przenieś wybrany parametr w górę i w dół listy
   | **Dodaj**        | Dodaj nowy parametr do listy
   | **Usuń**     | Usuń wybrany parametr z listy
   | **Modify**     | Zmodyfikuj wybrany parametr, zmieniając jego typ, nazwę i niezależnie od tego, czy jest on opcjonalny, i jakie wartości wprowadzano.
   | **Cofanie**     | Przywróć wybrany parametr jako oryginalny stan
   | **Przywróć wszystko** | Przywróć wszystkie parametry do ich oryginalnego stanu

   > [!TIP]
   > Użyj pola wyboru **Pomiń odwołanie w wersji zapoznawczej, jeśli wszystkie odwołania są zatwierdzone** , aby natychmiast wprowadzić zmiany bez okna podglądu usuwanie.

   Dodanie lub zmodyfikowanie parametru spowoduje wyświetlenie okna **Dodawanie parametru** lub **Edytowanie parametru** .

   ![Dodaj/Modyfikuj parametr](images/changesignature_addmodify.png)

   W tym miejscu można wykonać następujące czynności:

   | Wpis | Opis
   | ----- | ---
   | **Typ**               | Typ parametru (int, Double, float itp.)
   | **Nazwa**               | Nazwa parametru
   | **Parametr opcjonalny** | Sprawia, że parametr jest opcjonalnie określony
   | **Wartość wprowadzona**     | Wartość wstawiona do dowolnych wywołań do funkcji, w której parametr nie jest określony (prawidłowy tylko dla **dodania**)
   | **Wartość domyślna**      | Wartość używana przez funkcję, jeśli obiekt wywołujący nie określa jednego (prawidłowy dla **parametrów opcjonalnych**)

1. Użyj listy rozwijanej **zakres wyszukiwania** , aby wybrać, czy zmiany będą stosowane do projektu, czy całego rozwiązania.

1. Po zakończeniu kliknij przycisk **OK** , aby wprowadzić zmiany.  Upewnij się, że żądane zmiany są wprowadzane odpowiednio.  Użyj pól wyboru w górnej połowie okna, aby włączyć lub wyłączyć zmianę nazwy dowolnego elementu.

   ![Zmień podgląd sygnatur](images/changesignature_preview.png)

1. Gdy wszystko wygląda dobrze, kliknij przycisk **Zastosuj** , a funkcja zostanie zmieniona w kodzie źródłowym.

   ![Zmień wynik podpisu](images/changesignature_result.png)

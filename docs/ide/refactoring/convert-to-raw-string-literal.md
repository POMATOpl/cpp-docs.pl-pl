---
description: 'Dowiedz się więcej na temat: Konwertuj na literał nieprzetworzonego ciągu'
title: Konwertuj na literał nieprzetworzonego ciągu
ms.date: 11/16/2016
ms.assetid: fffbfee4-66ee-42ba-aeb9-df07fb702c51
ms.openlocfilehash: f83cb955bc2b30957306e1467a2d353377d5f33a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185560"
---
# <a name="convert-to-raw-string-literal"></a>Konwertuj na literał nieprzetworzonego ciągu

**Co:** Umożliwia włączenie dowolnego ciągu do literału nieprzetworzonego ciągu języka C++.

**Kiedy:** Istnieje ciąg z znakami ucieczki, które nie powinny być przetwarzane jako znaki ucieczki.

**Dlaczego:** Można wypróbować znaki podwójnej precyzji, ale często prowadzi to do mylących i nieczytelnych ciągów.  Użycie nieprzetworzonych literałów ciągu sprawia, że ciągi są znacznie łatwiejsze do odczytu.

**Jaka**

1. Umieść kursor tekstowy lub wskaźnik myszy nad ciągiem ucieczki do przekonwertowania.

   ![Wyróżniony kod](images/stringliteral_highlight.png)

1. Następnie wykonaj jedną z następujących czynności:
   * **Klawiatura**
     * Naciśnij **klawisze CTRL +.** Aby wyzwolić menu **szybkie akcje i operacje refaktoryzacji** , a następnie wybierz polecenie **Konwertuj na nieprzetworzony literał ciągu** z menu kontekstowego.
   * **Mysz**
     * Kliknij prawym przyciskiem myszy kod, wybierz menu **szybkie akcje i refaktoryzacje** i wybierz polecenie **Konwertuj na nieprzetworzony literał ciągu** z menu kontekstowego.
     * Kliknij ![ ikonę żarówki, ](images/bulb.png) która pojawia się na lewym marginesie, a następnie wybierz polecenie **Konwertuj na nieprzetworzony literał ciągu** z menu kontekstowego.

1. Ciąg zostanie natychmiast przekonwertowany na nieprzetworzony literał ciągu.

   ![Wynik literału nieprzetworzonego ciągu](images/stringliteral_result.png)

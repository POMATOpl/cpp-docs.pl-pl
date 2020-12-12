---
description: 'Dowiedz się więcej na temat: implementowanie czystych wirtualnych'
title: Implementuj czyste wirtualne
ms.date: 11/16/2016
ms.assetid: ea9b4719-34a3-474a-b4ec-05b1859f80f1
ms.openlocfilehash: b35ebba556ed9bae6ded649caca000b7d3554480
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318757"
---
# <a name="implement-pure-virtuals"></a>Implementuj czyste wirtualne

**Co:** Umożliwia natychmiastowe wygenerowanie kodu wymaganego do zaimplementowania wszystkich czystych metod wirtualnych w klasie.

**Kiedy:** Chcesz dziedziczyć z klasy przy użyciu czystych funkcji wirtualnych.

**Dlaczego:** Można ręcznie zaimplementować wszystkie czyste funkcje wirtualne jeden do jednego, jednak ta funkcja będzie automatycznie generować wszystkie podpisy metod.

**Jaka**

1. Umieść kursor tekstowy lub mysz nad klasą, w której chcesz zaimplementować czyste funkcje wirtualne klasy bazowej.

   ![Wyróżniony kod](images/virtuals_highlight.png)

1. Następnie wykonaj jedną z następujących czynności:
   * **Klawiatura**
     * Naciśnij **klawisze CTRL +.** Aby wyzwolić menu **szybkie akcje i refaktoryzacje** i wybrać opcję **Implementuj wszystkie czyste wirtualne dla klasy "*ClassName*"** z menu kontekstowego, gdzie *ClassName* jest nazwą wybranej klasy.
   * **Mysz**
     * Kliknij prawym przyciskiem myszy i wybierz menu **szybkie akcje i refaktoryzacje** i wybierz opcję **Implementuj wszystkie czyste wirtualne dla klasy "*ClassName*"** z menu kontekstowego, gdzie *ClassName* jest nazwą wybranej klasy.

1. Czyste podpisy metod wirtualnych zostaną utworzone automatycznie, gotowe do wdrożenia.

   ![Zaimplementuj czyste wyniki wirtualne](images/virtuals_result.png)

---
description: 'Dowiedz się więcej na temat: zmiana nazwy'
title: Zmień nazwę
ms.date: 11/16/2016
ms.assetid: 64b42a88-3bd9-4399-8b96-75bceffc353b
ms.openlocfilehash: 21bd5b817e51c29f4103b3ea105217ae743bdb4f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318731"
---
# <a name="rename"></a>Zmień nazwę

**Co:** Umożliwia zmianę nazw identyfikatorów dla symboli kodu, takich jak pola, zmienne lokalne, metody, przestrzenie nazw, właściwości i typy.

**Kiedy:** Chcesz bezpiecznie zmienić nazwę elementu bez konieczności znajdowania wszystkich wystąpień, a następnie skopiuj/wklej nową nazwę.

**Dlaczego:** Kopiowanie i wklejanie nowej nazwy w całym projekcie prawdopodobnie spowoduje błędy.  To narzędzie refaktoryzacji dokładnie przeprowadzi akcję zmiany nazwy.

**Jaka**

1. Podświetl lub umieść kursor tekstu wewnątrz elementu, którego nazwę chcesz zmienić:

   ![Wyróżniony kod](images/rename_highlight.png)

1. Następnie wykonaj jedną z następujących czynności:
   * **Klawiatura**
     * Naciśnij klawisze **Ctrl + r**, a następnie **Ctrl + r**.  (Pamiętaj, że skrót klawiaturowy może się różnić w zależności od wybranego profilu).
   * **Mysz**
     * Wybierz pozycję **edytuj > refaktoryzacja > Zmień nazwę**.
     * Kliknij prawym przyciskiem myszy kod i wybierz polecenie **Zmień nazwę**.

1. W oknie **zmiany nazwy** , które się pojawi, wprowadź nową nazwę wybranego elementu, a następnie kliknij przycisk **Podgląd** .  Zmień **zakres wyszukiwania** , jeśli trzeba rozszerzyć lub zawęzić zakres zmiany nazwy.

   ![Zmień nazwę okna dialogowego](images/rename_dialog.png)

   > [!TIP]
   > Możesz pominąć Podgląd, sprawdzając opcję **Pomijaj zmiany w wersji zapoznawczej, jeśli wszystkie odwołania są wszystkie potwierdzone** .

1. Gdy zostanie wyświetlone okno **Podgląd zmian — zmiana nazwy** , upewnij się, że żądane zmiany są wprowadzane odpowiednio.  Użyj pól wyboru w górnej połowie okna, aby włączyć lub wyłączyć zmianę nazwy dowolnego elementu.

   ![Zmień nazwę podglądu](images/rename_preview.png)

1. Gdy wszystko będzie wyglądało dobrze, kliknij przycisk **Zastosuj** , a element zostanie zmieniony na kod źródłowy.

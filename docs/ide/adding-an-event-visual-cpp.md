---
description: 'Dowiedz się więcej na temat: Dodawanie zdarzenia'
title: Dodawanie zdarzenia
ms.date: 11/12/2018
f1_keywords:
- vc.codewiz.event.overview
helpviewer_keywords:
- ActiveX controls [C++], adding events to
- MFC ActiveX controls [C++], adding events
- events [C++], ActiveX controls
- add event wizard [C++]
ms.assetid: fe34832a-edfc-4f86-aacb-8df77001873d
ms.openlocfilehash: c369be0fe241867b101ab458344ae706b1fd440d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97240822"
---
# <a name="add-an-event"></a>Dodawanie zdarzenia

Z Widok klasy można dodać zdarzenie przy użyciu [Kreatora dodawania zdarzenia](#add-event-wizard) tylko do klasy Control w projekcie [kontrolki ActiveX MFC](../mfc/reference/creating-an-mfc-activex-control.md) . Jeśli chcesz dodać zdarzenie do innego typu projektu, użyj przycisku **zdarzenia** w [okno właściwości](/visualstudio/ide/reference/properties-window).

**Aby dodać zdarzenie do projektu kontrolki ActiveX MFC:**

1. W Widok klasy rozwiń węzeł projektu, aby wyświetlić klasy w projekcie.

1. Kliknij prawym przyciskiem myszy klasę formantów projektu.

1. W menu skrótów wybierz polecenie **Dodaj**, a następnie wybierz polecenie **Dodaj zdarzenie** , aby wyświetlić Kreatora dodawania zdarzenia.

1. Podaj informacje o zdarzeniu w odpowiednich oknach kreatora.

1. Wybierz pozycję **Zakończ** , aby dodać zdarzenie do projektu.

## <a name="in-this-section"></a>W tej sekcji

- [Kreator dodawania zdarzenia](#add-event-wizard)

## <a name="add-event-wizard"></a>Kreator dodawania zdarzenia

Ten Kreator dodaje zdarzenie do projektu kontrolki ActiveX MFC. Możesz określić własne zdarzenie, dostosować typowe wydarzenie podstawowe lub wybrać opcję z listy wydarzeń giełdowych.

- **Nazwa zdarzenia**

   Ustawia nazwę używaną przez klientów usługi Automation do żądania zdarzenia od klasy. Wprowadź nazwę lub wybierz ją z listy.

- **Typ zdarzenia**

   Wskazuje typ zdarzenia do dodania. Dostępne tylko w przypadku wybrania z listy **Nazwa zdarzenia** .

   |Opcja|Opis|
   |------------|-----------------|
   |**Stanu**|Określa, że dla tej klasy zostanie zaimplementowane wydarzenie podstawowe, takie jak przycisk. Zdarzenia giełdowe są zdefiniowane w bibliotece Microsoft Foundation Class (MFC).|
   |**Niestandardowe**|Określa, że używasz własnej implementacji zdarzenia.|

- **Nazwa wewnętrzna**

   Ustawia nazwę funkcji składowej, która wysyła zdarzenie. Dostępne tylko dla zdarzeń niestandardowych. Nazwa jest oparta na **nazwie zdarzenia**. Można zmienić nazwę wewnętrzną, jeśli chcesz podać nazwę inną niż **Nazwa zdarzenia**.

- **Typ parametru**

   Ustawia typ **nazwy parametru**. Wybierz typ z listy.

- **Nazwa parametru**

   Ustawia nazwę parametru, który ma zostać przekazany przez zdarzenie. Po wpisaniu nazwy, należy wybrać pozycję **Dodaj** , aby dodać ją do listy parametrów.

   Po wybraniu opcji **Dodaj** Nazwa parametru zostanie wyświetlona na **liście parametrów**.

   > [!NOTE]
   > Jeśli podasz nazwę parametru, a następnie wybierz pozycję **Zakończ** przed wybraniem opcji **Dodaj**, parametr nie zostanie dodany do zdarzenia. Należy znaleźć metodę i wstawić parametr ręcznie.

- **Dodaj**

   Dodaje parametr określony w polu **Nazwa parametru** oraz jego typ do **listy parametrów**. Wybierz pozycję **Dodaj** , aby dodać parametr do listy.

- **Usuń**

   Usuwa parametr wybrany na **liście parametrów** z listy.

- **Lista parametrów**

   Wyświetla wszystkie parametry i ich typy, które są obecnie dodawane do metody. Podczas dodawania parametrów Kreator aktualizuje **listę parametrów** , aby wyświetlić każdy parametr z typem.

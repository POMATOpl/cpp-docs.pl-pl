---
description: 'Dowiedz się więcej na temat: Tworzenie klasy okien dialogowych'
title: Tworzenie klasy okien dialogowych
ms.date: 09/06/2019
helpviewer_keywords:
- dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- files [MFC], creating
- dialog classes [MFC], Add Class Wizard
- dialog classes [MFC], creating
ms.assetid: d5321741-da41-47a8-bb1c-6a0e8b28c4c1
ms.openlocfilehash: d135d6acaefbc73f435e48db8f72add7081fdac2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309449"
---
# <a name="creating-your-dialog-class"></a>Tworzenie klasy okien dialogowych

Dla każdego okna dialogowego w programie Utwórz nową klasę okna dialogowego do pracy z zasobem okna dialogowego.

[Dodanie klasy](../ide/adding-a-class-visual-cpp.md) wyjaśnia, jak utworzyć nową klasę okna dialogowego. Podczas tworzenia klasy okien dialogowych za pomocą [kreatora klas](reference/mfc-class-wizard.md)zapisuje następujące elementy w określonych plikach. h i. cpp:

W pliku h:

- Deklaracja klasy dla klasy okna dialogowego. Klasa pochodzi od [CDialog](reference/cdialog-class.md).

W pliku. cpp:

- Mapa komunikatów dla klasy.

- Standardowy Konstruktor dla okna dialogowego.

- Przesłonięcie funkcji składowej [DoDataExchange](reference/cwnd-class.md#dodataexchange) . Edytuj tę funkcję. Służy do wymiany i sprawdzania poprawności danych w oknie dialogowym zgodnie z opisem w dalszej części [okna dialogowego wymiana danych i sprawdzanie poprawności](dialog-data-exchange-and-validation.md).

## <a name="see-also"></a>Zobacz też

[Tworzenie klasy okien dialogowych za pomocą kreatorów kodu](creating-a-dialog-class-with-code-wizards.md)<br/>
[Praca z oknami dialogowymi w MFC](life-cycle-of-a-dialog-box.md)

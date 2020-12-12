---
description: 'Dowiedz się więcej o: Przesłoń funkcję wirtualną'
title: Przesłanianie funkcji wirtualnej
ms.date: 11/12/2018
f1_keywords:
- vc.codewiz.virtualfunc.override
helpviewer_keywords:
- virtual functions, overriding
- base classes, overriding virtual functions defined in
- Properties window, overriding virtual functions in
ms.assetid: 2d8c76f2-7a6b-4c9c-8de5-4282ce7755b6
ms.openlocfilehash: d4c800006d5227ed5397c17284c03968a24a3964
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335911"
---
# <a name="override-a-virtual-function"></a>Przesłanianie funkcji wirtualnej

Można przesłonić funkcje wirtualne zdefiniowane w klasie bazowej z [okno właściwości](/visualstudio/ide/reference/properties-window)programu Visual Studio.

**Aby zastąpić funkcję wirtualną w okno Właściwości:**

1. W Widok klasy wybierz klasę.

1. W okno Właściwości wybierz przycisk **zastąpień** .

   > [!NOTE]
   > Przycisk **zastąpień** jest dostępny po wybraniu nazwy klasy w widok klasy lub po wybraniu w oknie źródłowym.

   W lewej kolumnie znajduje się lista funkcji wirtualnych. Jeśli nazwa funkcji wirtualnej pojawia się również w prawej kolumnie, przesłonięcie zostało już zaimplementowane.

1. Jeśli funkcja nie ma zastąpień, zaznacz komórkę w prawej kolumnie w okno Właściwości, aby wyświetlić sugerowaną nazwę przesłonięcia funkcji jako \<add> *FuncName*.

1. Wybierz sugerowaną nazwę, aby dodać kod zastępczy dla funkcji.

1. Aby edytować funkcję zastępującą, kliknij dwukrotnie nazwę funkcji w Widok klasy i edytuj kod w oknie źródłowym.

Aby usunąć przesłonięcie, wybierz nazwę funkcji zastąpienia w prawej kolumnie, a następnie wybierz pozycję \<delete> *FuncName*. Kod funkcji jest oznaczony jako komentarz.

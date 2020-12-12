---
description: 'Dowiedz się więcej o: błąd kompilatora C2696'
title: Błąd kompilatora C2696
ms.date: 11/04/2016
f1_keywords:
- C2696
helpviewer_keywords:
- C2696
ms.assetid: 6c6eb7df-1230-4346-9a73-abf14c20785d
ms.openlocfilehash: 2d4a798258ba6f9bb467c4da32e75860b96874e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326618"
---
# <a name="compiler-error-c2696"></a>Błąd kompilatora C2696

Nie można utworzyć obiektu tymczasowego typu zarządzanego "Type".

Odwołania do **`const`** programu w niezarządzanym programie powodują wywołanie konstruktora przez kompilator i utworzenie obiektu tymczasowego na stosie. Jednak klasy zarządzanej nigdy nie można utworzyć na stosie.

C2696 jest osiągalna tylko przy użyciu przestarzałej opcji kompilatora **/CLR: oldSyntax**.

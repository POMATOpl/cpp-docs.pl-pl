---
description: 'Dowiedz się więcej o: błąd kompilatora C2818'
title: Błąd kompilatora C2818
ms.date: 11/04/2016
f1_keywords:
- C2818
helpviewer_keywords:
- C2818
ms.assetid: 715fc7c9-0c6d-452b-b7f5-1682cea5e907
ms.openlocfilehash: e258387af290a8070c1c66a56a7523b46482cf99
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194790"
---
# <a name="compiler-error-c2818"></a>Błąd kompilatora C2818

Aplikacja przeciążonego "operator->" jest rekursywna za poorednictwem typu "Type"

Ponowna definicja operatora dostępu do składowej klasy zawiera instrukcję cykliczną **`return`** . Aby ponownie zdefiniować `->` operator z rekursją, należy przenieść procedurę cykliczną do osobnej funkcji o nazwie z funkcji przesłaniania operatora.

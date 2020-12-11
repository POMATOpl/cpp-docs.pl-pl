---
description: 'Dowiedz się więcej o: błąd kompilatora C3550'
title: Błąd kompilatora C3550
ms.date: 11/04/2016
f1_keywords:
- C3550
helpviewer_keywords:
- C3550
ms.assetid: 9f2d5ffc-e429-41a1-89e3-7acc4fd47e14
ms.openlocfilehash: 4cb459e3f8e7fdd0dbb00c1d4dfaa3c3c6b1eb71
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97112417"
---
# <a name="compiler-error-c3550"></a>Błąd kompilatora C3550

w tym kontekście jest dozwolony tylko zwykły element "decltype (Auto)"

Jeśli `decltype(auto)` jest używany jako symbol zastępczy dla zwracanego typu funkcji, musi być używany przez samą siebie. Nie można jej użyć jako części deklaracji wskaźnika ( `decltype(auto*)` ), deklaracji odwołania ( `decltype(auto&)` ) ani innych takich kwalifikacji.

## <a name="see-also"></a>Zobacz też

[Automatycznie](../../cpp/auto-cpp.md)

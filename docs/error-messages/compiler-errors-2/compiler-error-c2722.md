---
title: Błąd kompilatora C2722
ms.date: 11/04/2016
f1_keywords:
- C2722
helpviewer_keywords:
- C2722
ms.assetid: 4cc2c7fa-cb12-4bcf-9df1-6d627ef62973
ms.openlocfilehash: 4274ac6ec33e0176f998fcf5a2b3efd570a4009f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383038"
---
# <a name="compiler-error-c2722"></a>Błąd kompilatora C2722

":: operator': niedozwolony po polecenia operatora; Użyj "operator operator"

`operator` Instrukcji ponownie zdefiniowanych wystąpień `::new` lub `::delete`. `new` i `delete` operatory są globalne, więc operatora rozpoznawania zakresu (`::`) jest bez znaczenia. Usuń `::` operatora.
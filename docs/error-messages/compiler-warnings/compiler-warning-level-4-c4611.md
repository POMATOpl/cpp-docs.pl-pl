---
title: Kompilator ostrzeżenie (poziom 4) C4611 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4611
dev_langs:
- C++
helpviewer_keywords:
- C4611
ms.assetid: bd90d0a6-75f9-4e97-968d-dda6773e9fd8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 723976dc8b7085ede9b3157445ff3026de6fc4b9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091052"
---
# <a name="compiler-warning-level-4-c4611"></a>Kompilator ostrzeżenie (poziom 4) C4611

Interakcja między "function" i zniszczeniem obiektu języka C++ nie jest przenośna

Na niektórych platformach funkcje, które obejmują **catch** mogą nie obsługiwać semantyki obiektów języka C++ likwidacji, gdy komputer znajduje się poza zakresem.

Aby uniknąć nieoczekiwanego zachowania, należy unikać **catch** w funkcjach, które mają konstruktory i destruktory.

To ostrzeżenie zostanie wyświetlone tylko raz; zobacz [warning elementu pragma](../../preprocessor/warning.md).
---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1509'
title: Błąd krytyczny C1509
ms.date: 11/04/2016
f1_keywords:
- C1509
helpviewer_keywords:
- C1509
ms.assetid: 40dd100d-c6ba-451c-bd26-2c99ec1c36d6
ms.openlocfilehash: dc2483ae96f599912b3ba6d1594257fec81ac251
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276351"
---
# <a name="fatal-error-c1509"></a>Błąd krytyczny C1509

ograniczenie kompilatora: zbyt wiele stanów obsługi wyjątków w funkcji "Function". Uprość funkcję

Kod przekracza limit wewnętrzny w Stanach obsługi wyjątków (32 768 Stany).

Najbardziej typową przyczyną jest to, że funkcja zawiera złożone wyrażenie zmiennych klas zdefiniowanych przez użytkownika i operatorów arytmetycznych.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aby rozwiązać ten problem, można użyć następujących rozwiązań

1. Uprość wyrażenia przez przypisanie wspólnych podwyrażeń do zmiennych tymczasowych.

1. Podziel funkcję na mniejsze funkcje.

---
description: 'Dowiedz się więcej o: błąd kompilatora C3888'
title: Błąd kompilatora C3888
ms.date: 11/04/2016
f1_keywords:
- C3888
helpviewer_keywords:
- C3888
ms.assetid: 40820812-79c5-4dcd-a19d-b4164d25fc8a
ms.openlocfilehash: 5b47d78d0d6c75f4bdd266f95fff2ce4ab025d4f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97274323"
---
# <a name="compiler-error-c3888"></a>Błąd kompilatora C3888

"name": wyrażenie const skojarzone z tym literałem składowej danych nie jest obsługiwane przez C++/CLI

*Nazwa* elementu członkowskiego danych zadeklarowanego za pomocą słowa kluczowego [Literal](../../extensions/literal-cpp-component-extensions.md) jest inicjowana z wartością, której kompilator nie obsługuje. Kompilator obsługuje tylko stałe typy całkowite, wyliczenia lub String. Najprawdopodobniej przyczyną błędu **C3888** jest zainicjowanie składowej danych z tablicą bajtów.

### <a name="to-correct-this-error"></a>Aby poprawić ten błąd

1. Sprawdź, czy zadeklarowany element członkowski danych jest obsługiwany.

## <a name="see-also"></a>Zobacz też

[wpisać](../../extensions/literal-cpp-component-extensions.md)

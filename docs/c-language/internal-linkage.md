---
description: 'Dowiedz się więcej na temat: połączenie wewnętrzne'
title: Połączenie wewnętrzne
ms.date: 11/04/2016
helpviewer_keywords:
- internal linkage
- linkage [C++], internal
ms.assetid: 80be7b51-c930-43db-94d6-4f09a64077bf
ms.openlocfilehash: a22de598f119ec303cb7ea78255c2537c6ed306e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97181868"
---
# <a name="internal-linkage"></a>Połączenie wewnętrzne

Jeśli deklaracja identyfikatora zakresu plików dla obiektu lub funkcji zawiera *specyfikator klasy magazynu* **`static`** , identyfikator ma wewnętrzny związek... W przeciwnym razie identyfikator ma powiązania zewnętrzne. Zobacz [klasy magazynu](../c-language/c-storage-classes.md) , aby zapoznać się z omówieniem nieterminalu *specyfikatora klasy Storage* .

W jednej jednostce translacji każde wystąpienie identyfikatora z wewnętrznym powiązaniem oznacza ten sam identyfikator lub funkcję. Wewnętrznie połączone identyfikatory są unikatowe dla jednostki tłumaczenia.

## <a name="see-also"></a>Zobacz też

[Użycie zewnętrznie w celu określenia powiązania](../cpp/extern-cpp.md)

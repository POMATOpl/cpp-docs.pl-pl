---
description: 'Dowiedz się więcej o: zalety zestawu wbudowanego'
title: Zalety wbudowanego asemblera
ms.date: 08/30/2018
helpviewer_keywords:
- assembler [C++], advantages
- inline assembly [C++], about inline assembly
- inline assembly [C++], using
ms.assetid: 94364d97-faa7-4bdf-8473-570956986c51
ms.openlocfilehash: 066824a4ad63641f33712219dd8364b0edf7259b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118072"
---
# <a name="advantages-of-inline-assembly"></a>Zalety wbudowanego asemblera

**Specyficzne dla firmy Microsoft**

Ponieważ wbudowany asembler nie wymaga oddzielnego zestawu i kroków łączy, jest bardziej wygodne niż oddzielny asembler. Wbudowany kod asemblera może używać dowolnej zmiennej języka C lub nazwy funkcji, która znajduje się w zakresie, dzięki czemu można łatwo zintegrować ją z kodem C programu. Ponieważ kod zestawu może być mieszany w instrukcji języka C lub C++, może wykonywać zadania, które są uciążliwe lub niemożliwe w języku C lub C++.

Użycie zestawu wbudowanego obejmuje:

- Pisanie funkcji w języku asemblera.

- Optymalizacja w poziomie — najważniejsze sekcje kodu.

- Umożliwienie bezpośredniego dostępu do sprzętu dla sterowników urządzeń.

- Pisanie kodu prologu i epilogu dla wywołań "owies".

Wbudowany zestaw jest narzędziem specjalnego przeznaczenia. Jeśli planujesz port aplikacji na różnych maszynach, prawdopodobnie chcesz umieścić kod specyficzny dla maszyny w osobnym module. Ponieważ wbudowany asembler nie obsługuje wszystkich dyrektyw i danych makr asemblera (MASM) firmy Microsoft, przydatne może okazać się użycie MASM dla takich modułów.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Asembler wbudowany](../../assembler/inline/inline-assembler.md)<br/>

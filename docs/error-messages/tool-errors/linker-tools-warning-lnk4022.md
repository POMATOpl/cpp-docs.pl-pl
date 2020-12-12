---
description: 'Dowiedz się więcej o: LNK4022 narzędzi KONSOLIDATORA ostrzeżenia narzędzi konsolidatora'
title: Ostrzeżenie LNK4022 narzędzi konsolidatora
ms.date: 11/04/2016
f1_keywords:
- LNK4022
helpviewer_keywords:
- LNK4022
ms.assetid: 890f487e-db98-45dd-a226-c7ccead82b1e
ms.openlocfilehash: f0f968bf8e562d87e2227fb67f7a37b450c813b1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331938"
---
# <a name="linker-tools-warning-lnk4022"></a>Ostrzeżenie LNK4022 narzędzi konsolidatora

nie można znaleźć unikatowego dopasowania dla symbolu "symbol"

LINK lub biblioteka LIB znalazła wiele dopasowań dla danego niedekoracyjnego symbolu i nie może rozpoznać niejednoznaczności. Nie jest tworzony plik wyjściowy (exe, DLL,. EXP lub. lib). Po tym ostrzeżeniu następuje jedno ostrzeżenie [LNK4002 narzędzi konsolidatora](../../error-messages/tool-errors/linker-tools-warning-lnk4002.md) dla każdego zduplikowanego symbolu i ostatecznie następuje błąd krytyczny [LNK1152](../../error-messages/tool-errors/linker-tools-error-lnk1152.md).

Aby uniknąć tego ostrzeżenia, należy określić symbol w postaci dekoracyjnej. Uruchom [polecenia DUMPBIN](../../build/reference/dumpbin-options.md) na obiekcie, aby zobaczyć dekoracyjne nazwy.

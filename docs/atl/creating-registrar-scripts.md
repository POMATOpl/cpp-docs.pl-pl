---
description: Dowiedz się więcej na temat tworzenia skryptów rejestratora
title: Tworzenie skryptów dla rejestratora ATL
ms.date: 05/14/2014
helpviewer_keywords:
- scripting, registry scripting
- ATL, registry
- registrar scripts [ATL]
- scripts, Registrar scripts
- scripts, creating
ms.assetid: cbd5024b-8061-4a71-be65-7fee90374a35
ms.openlocfilehash: a3ce4855460e65eda5ab522bc16f39191da02a71
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153190"
---
# <a name="creating-registrar-scripts"></a>Tworzenie skryptów rejestratora

Skrypt rejestratora zapewnia oparte na danych, a nie oparty na interfejsie API, dostęp do rejestru systemowego. Dostęp oparty na danych jest zazwyczaj bardziej wydajny, ponieważ do dodawania klucza do rejestru jest potrzebny tylko jeden lub dwa wiersze w skrypcie.

[Kreator kontrolki ATL](../atl/reference/atl-control-wizard.md) automatycznie generuje skrypt rejestratora dla serwera com. Ten skrypt można znaleźć w pliku RGS skojarzonym z obiektem.

Aparat skryptów rejestratora ATL przetwarza skrypt rejestratora w czasie wykonywania. ATL automatycznie wywołuje aparat skryptów podczas instalacji serwera.

W tym artykule omówiono następujące tematy związane ze skryptami rejestratora:

- [Opis składni notacji Backusa-Naura (BNF)](../atl/understanding-backus-naur-form-bnf-syntax.md)

- [Omówienie drzew analizy](../atl/understanding-parse-trees.md)

- [Przykłady skryptów rejestru](../atl/registry-scripting-examples.md)

- [Używanie parametrów wymiennych (preprocesora rejestratora)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)

- [Wywoływanie skryptów](../atl/invoking-scripts.md)

## <a name="see-also"></a>Zobacz też

[Składnik rejestru (Rejestrator)](../atl/atl-registry-component-registrar.md)

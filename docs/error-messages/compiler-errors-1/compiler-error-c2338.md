---
description: 'Dowiedz się więcej o: błąd kompilatora C2338'
title: Błąd kompilatora C2338
ms.date: 11/04/2016
f1_keywords:
- C2338
helpviewer_keywords:
- C2338
ms.assetid: 49bba575-1de4-4963-86c6-ce3226a2ba51
ms.openlocfilehash: 7bbbc7fd6240fce2def470a0d16aa0dba152a109
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234803"
---
# <a name="compiler-error-c2338"></a>Błąd kompilatora C2338

> *Komunikat o błędzie*

Ten błąd może być spowodowany **`static_assert`** błędem podczas kompilacji. Komunikat jest dostarczany przez **`static_assert`** parametry.

Ten komunikat o błędzie może być również generowany przez zewnętrznych dostawców do kompilatora. W większości przypadków te błędy są zgłaszane przez bibliotekę DLL dostawcy atrybutów, taką jak ATLPROV. Niektóre typowe formy tego komunikatu obejmują:

- "*Attribute*" — dostawca atrybutów ATL: błąd *komunikatu* o *numerze* ATL

- Nieprawidłowe użycie atrybutu "*Attribute*"

- "*użycie*": niepoprawny format atrybutu "Usage"

Te błędy są często nieodwracalne i mogą następować krytyczne błędy kompilatora.

Aby rozwiązać te problemy, Popraw użycie atrybutu. Na przykład w niektórych przypadkach parametry atrybutu muszą być zadeklarowane, aby można było ich używać. Jeśli zostanie podany numer błędu ATL, zapoznaj się z dokumentacją tego błędu, aby uzyskać bardziej szczegółowe informacje.

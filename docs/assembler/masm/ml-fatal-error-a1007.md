---
description: 'Dowiedz się więcej o: błąd krytyczny ML A1007'
title: Błąd krytyczny ML A1007
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A1007
helpviewer_keywords:
- A1007
ms.assetid: bcf9c826-beb3-4e93-91fe-1ffd34995fbf
ms.openlocfilehash: c26d5de1c1b44fb37d4a95f51b2cb9480d2ba664
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97129548"
---
# <a name="ml-fatal-error-a1007"></a>Błąd krytyczny ML A1007

**zbyt głęboki poziom zagnieżdżenia**

Asembler osiągnął limit zagnieżdżenia. Limit wynosi 20 poziomów, chyba że zaznaczono inaczej.

Jeden z następujących elementów został zagnieżdżony zbyt głęboko:

- Dyrektywa wysokiego poziomu, taka jak [. Jeśli](dot-if.md), [. Powtórz](dot-repeat.md)lub [. WHILE](dot-while.md).

- Definicja struktury.

- Dyrektywa zestawu warunkowego.

- Definicja procedury.

- Dyrektywa [PUSHCONTEXT](pushcontext.md) (limit wynosi 10).

- Definicja segmentu.

- Plik dołączany.

- Makro.

## <a name="see-also"></a>Zobacz też

[Komunikaty o błędach ML](ml-error-messages.md)

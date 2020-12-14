---
description: 'Dowiedz się więcej: wywnioskowane zależności i reguły'
title: Zależności wywnioskowane oraz zasady
ms.date: 11/04/2016
helpviewer_keywords:
- rules, inferred
- inferred dependents in NMAKE
- inferred rules in NMAKE
- dependents, inferred
ms.assetid: 9381e74a-53d9-445c-836d-0ff7ef6112d9
ms.openlocfilehash: 9f4c1d14d18c9c693a7bd71f9207ff36aede8e22
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191280"
---
# <a name="inferred-dependents-and-rules"></a>Zależności wywnioskowane oraz zasady

NMAKE zakłada wywnioskowane zależne dla elementu docelowego, jeśli istnieje odpowiednia reguła wnioskowania. Reguła ma zastosowanie, jeśli:

- *toext* dopasowuje rozszerzenie elementu docelowego.

- *fromext* dopasowuje rozszerzenie pliku, który ma nazwę bazową obiektu docelowego i istnieje w bieżącym lub określonym katalogu.

- *fromext* jest w [. SUFIKSy](dot-directives.md); żadne inne *fromext* w regule dopasowania nie mają wyższego poziomu **. Priorytet SUFIKSów** .

- Brak jawnych elementów zależnych ma wyższy poziom **. Priorytet SUFIKSów** .

Wywnioskowane zależności mogą spowodować nieoczekiwane skutki uboczne. Jeśli blok opisu elementu docelowego zawiera polecenia, NMAKE wykonuje te polecenia zamiast poleceń w regule.

## <a name="see-also"></a>Zobacz też

[Zasady wnioskowania](inference-rules.md)

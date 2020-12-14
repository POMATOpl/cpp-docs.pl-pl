---
description: 'Dowiedz się więcej o: definiowaniu reguły'
title: Definiowanie zasady
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, inference rules
- defining inference rules
ms.assetid: 071cd092-3f2e-4065-b0fb-36a9d393cfa8
ms.openlocfilehash: 89a5db90162ede02743aa469ac4f9e3d75c5e147
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201680"
---
# <a name="defining-a-rule"></a>Definiowanie zasady

*Fromext* reprezentuje rozszerzenie pliku zależnego, a *toext* reprezentuje rozszerzenie pliku docelowego.

```
.fromext.toext:
   commands
```

## <a name="remarks"></a>Uwagi

W przypadku rozszerzeń nie jest uwzględniana wielkość liter. Makra mogą być wywoływane do reprezentowania *fromext* i *toext*; makra są rozszerzane podczas przetwarzania wstępnego. Kropka (.) poprzedzająca *fromext* musi pojawić się na początku wiersza. Dwukropek (:) jest poprzedzony przez zero lub więcej spacji lub kart. Może wystąpić tylko spacje lub tabulatory, średnik (;) Aby określić polecenie, znak numeru (#) do określenia komentarza lub znaku nowego wiersza. Nie są dozwolone żadne inne spacje. Polecenia są określone jako bloki opisu.

## <a name="what-do-you-want-to-know-more-about"></a>Jak chcesz dowiedzieć się więcej?

[Ścieżki wyszukiwania w zasadach](search-paths-in-rules.md)

## <a name="see-also"></a>Zobacz też

[Zasady wnioskowania](inference-rules.md)

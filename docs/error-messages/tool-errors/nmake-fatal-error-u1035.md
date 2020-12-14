---
description: 'Dowiedz się więcej na temat: błąd krytyczny NMAKE U1035'
title: Błąd krytyczny NMAKE U1035
ms.date: 11/04/2016
f1_keywords:
- U1035
helpviewer_keywords:
- U1035
ms.assetid: 68f0cc59-007e-4109-ac30-7ac4ac447e6d
ms.openlocfilehash: e41b65cbec43a0b19e06767c555df9cfede9b69c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197754"
---
# <a name="nmake-fatal-error-u1035"></a>Błąd krytyczny NMAKE U1035

Błąd składniowy: oczekiwano separatora ":" lub "="

Oczekiwano dwukropek (**:**) lub znaku równości ( **=** ).

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aby rozwiązać ten problem, sprawdzając następujące możliwe przyczyny

1. Dwukropek nie podążał za obiektem docelowym.

1. Dwukropek i bez spacji (na przykład:) wykonano jednoliterowy element docelowy. NMAKE go jako specyfikację dysku.

1. Dwukropek nie przestrzegał reguły wnioskowania.

1. Po definicji makra nie następują znaku równości.

1. Znak jest ukośnikiem odwrotnym ( **\\** ), który został użyty do kontynuowania polecenia do nowego wiersza.

1. Pojawił się ciąg, który nie jest zgodny z żadną regułą składni NMAKE.

1. Plik reguł programu make został sformatowany przez Edytor tekstów.

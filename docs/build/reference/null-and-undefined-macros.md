---
description: 'Dowiedz się więcej o: puste i niezdefiniowane makra'
title: Makra niezdefiniowane oraz makra o wartości zerowej
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, undefined macros
- Null macros in NMAKE
- macros, null and undefined
- undefined macros and NMAKE
- NMAKE program, null macros
ms.assetid: 1db4611a-1755-4328-b00f-d35365af8b6c
ms.openlocfilehash: 639afda727f1ebb1f4d7d602ed7cf01d6c914a33
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209727"
---
# <a name="null-and-undefined-macros"></a>Makra niezdefiniowane oraz makra o wartości zerowej

Makra o wartości null i undefines są rozwijane do ciągów o wartości null, ale makro zdefiniowane jako ciąg o wartości null jest uznawane za zdefiniowane w wyrażeniach przetwarzania wstępnego. Aby zdefiniować makro jako ciąg pusty, należy określić brak znaków z wyjątkiem spacji lub tabulatorów po znaku równości (=) w wierszu polecenia lub pliku polecenia i ująć ciąg null lub definicję w podwójny cudzysłów (""). Aby wydefiniować makro, użyj **! UNDEF.** Aby uzyskać więcej informacji, zobacz [dyrektywy wstępnego przetwarzania plików reguł programu make](makefile-preprocessing-directives.md).

## <a name="see-also"></a>Zobacz też

[Definiowanie makra NMAKE](defining-an-nmake-macro.md)

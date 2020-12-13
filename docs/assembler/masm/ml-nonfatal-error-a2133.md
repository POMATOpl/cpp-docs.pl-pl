---
description: 'Dowiedz się więcej o: błąd niekrytyczny ML A2133'
title: Błąd niekrytyczny ML A2133
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A2133
helpviewer_keywords:
- A2133
ms.assetid: 5ba50911-22c8-43b7-90e2-946fc612e05f
ms.openlocfilehash: 11a2d27a00ac4e1d8b669ec7a7d4fe523476b5c4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97128469"
---
# <a name="ml-nonfatal-error-a2133"></a>Błąd niekrytyczny ML A2133

**wartość rejestru zastąpiona przez wywołanie**

Rejestr został przekazany jako argument do procedury, ale kod wygenerowany przez metodę [Invoke](invoke.md) , aby przekazać inne argumenty zniszczone zawartość rejestru.

Rejestry AX, AL, AH, EAX, DX, DL, DH i EDX mogą być używane przez asembler do wykonywania konwersji danych.

Użyj innego rejestru.

## <a name="see-also"></a>Zobacz też

[Komunikaty o błędach ML](ml-error-messages.md)

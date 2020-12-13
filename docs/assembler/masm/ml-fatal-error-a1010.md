---
description: 'Dowiedz się więcej o: błąd krytyczny ML A1010'
title: Błąd krytyczny ML A1010
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A1010
helpviewer_keywords:
- A1010
ms.assetid: 9e0b5241-67f4-4740-8701-3b2d2d1ad9e4
ms.openlocfilehash: 4a00d9594c71c8a22942e869d109bf51176394c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97129509"
---
# <a name="ml-fatal-error-a1010"></a>Błąd krytyczny ML A1010

**niedopasowane zagnieżdżenie bloków:**

Początek bloku nie ma pasującego końca lub zakończenie bloku nie ma pasującego początku. Może być uwzględniona jedna z następujących elementów:

- Dyrektywa wysokiego poziomu, taka jak [. Jeśli](dot-if.md), [. Powtórz](dot-repeat.md)lub [. WHILE](dot-while.md).

- Dyrektywa zestawu warunkowego, taka jak [if](if-masm.md), [REPEAT](repeat.md)lub **while**.

- Struktura lub definicja związku.

- Definicja procedury.

- Definicja segmentu.

- Dyrektywa [POPCONTEXT](popcontext.md) .

- Dyrektywa zestawu warunkowego, taka jak [else](else-masm.md), [ElseIf](elseif-masm.md)lub **endif** bez dopasowania [if](if-masm.md).

## <a name="see-also"></a>Zobacz też

[Komunikaty o błędach ML](ml-error-messages.md)

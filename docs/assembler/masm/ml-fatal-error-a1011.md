---
description: 'Dowiedz się więcej o: błąd krytyczny ML A1011'
title: Błąd krytyczny ML A1011
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A1011
helpviewer_keywords:
- A1011
ms.assetid: 7fbf092d-4189-4330-a884-dfa2268fc3dd
ms.openlocfilehash: 294ca2cbf512948514317589628969a3e63e71af
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97129496"
---
# <a name="ml-fatal-error-a1011"></a>Błąd krytyczny ML A1011

**dyrektywa musi być w bloku sterowania**

Asembler znalazł dyrektywę wysokiego poziomu, której nie oczekiwano. Znaleziono jedną z następujących dyrektyw:

- [. INACZEJ](dot-else.md) bez [. Jeśli](dot-if.md)

- [. ENDIF](dot-endif.md) bez [. Jeśli](dot-if.md)

- [. ENDW](dot-endw.md) bez [. WHILE](dot-while.md)

- [. UNTILCXZ](dot-untilcxz.md) bez [. Powtórz](dot-repeat.md)

- [. Kontynuuj](dot-continue.md) bez [. WHILE](dot-while.md) lub [. Powtórz](dot-repeat.md)

- [. Przerwij](dot-break.md) bez [. WHILE](dot-while.md) lub [. Powtórz](dot-repeat.md)

- [. ELSE](dot-else.md) : `.ELSE`

## <a name="see-also"></a>Zobacz też

[Komunikaty o błędach ML](ml-error-messages.md)

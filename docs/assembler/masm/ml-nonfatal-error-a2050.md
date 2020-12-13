---
description: 'Dowiedz się więcej o: błąd niekrytyczny ML A2050'
title: Błąd niekrytyczny ML A2050
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A2050
helpviewer_keywords:
- A2050
ms.assetid: 16f3a58f-4bde-48f1-b0e3-2ed9612780a5
ms.openlocfilehash: 9ae38353d3c2e2a2e25e3e5c4a87e3b3b6888781
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97129002"
---
# <a name="ml-nonfatal-error-a2050"></a>Błąd niekrytyczny ML A2050

**Liczba rzeczywistych lub BCD nie jest dozwolona**

Stała liczba zmiennoprzecinkowa (rzeczywista) lub zakodowana cyfra dziesiętna (BCD) została użyta inna niż inicjator danych.

Wystąpił jeden z następujących:

- W wyrażeniu użyto liczby rzeczywistej lub BCD.

- Liczba rzeczywista została użyta do zainicjowania dyrektywy innej niż [DWORD](dword.md), [Qword](qword.md)lub [TBYTE](tbyte.md).

- BCD został użyty do zainicjowania dyrektywy innej niż `TBYTE` .

## <a name="see-also"></a>Zobacz też

[Komunikaty o błędach ML](ml-error-messages.md)

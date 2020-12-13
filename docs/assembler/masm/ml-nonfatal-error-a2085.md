---
description: 'Dowiedz się więcej o: błąd niekrytyczny ML A2085'
title: Błąd niekrytyczny ML A2085
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A2085
helpviewer_keywords:
- A2085
ms.assetid: c2fef415-a32b-4249-896c-6d981fc6e327
ms.openlocfilehash: 3a2cd89b373f761beb3fc0de01a1bea3ec7bf82e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97128548"
---
# <a name="ml-nonfatal-error-a2085"></a>Błąd niekrytyczny ML A2085

**instrukcja lub rejestr nie został zaakceptowany w bieżącym trybie procesora**

Podjęto próbę użycia instrukcji, rejestru lub słowa kluczowego, które były nieprawidłowe dla bieżącego trybu procesora.

Na przykład rejestry 32-bitowe wymagają [. 386](dot-386.md) lub nowszego. Rejestry kontroli, takie jak CR0, wymagają trybu uprzywilejowanego [. 386P](dot-386p.md) lub wyższe. Ten błąd zostanie również wygenerowany dla **NEAR32**, **FAR32** i **zwykłych** słów kluczowych, które wymagają. **386** lub nowszy.

## <a name="see-also"></a>Zobacz też

[Komunikaty o błędach ML](ml-error-messages.md)

---
description: 'Dowiedz się więcej o programie: przerywanie'
title: Użycie przerywania
ms.date: 11/04/2016
helpviewer_keywords:
- abort function
ms.assetid: 3ba39b78-ef74-4a8d-8dee-2d62442de174
ms.openlocfilehash: 16c1df7a7b3a26be444d9b17d370366b1a41ea1f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116863"
---
# <a name="using-abort"></a>Użycie przerywania

Wywołanie funkcji [Abort](../c-runtime-library/reference/abort.md) powoduje natychmiastowe zakończenie. Pomija proces normalnego niszczenia dla zainicjowanych globalnych obiektów statycznych. Pomija również specjalne przetwarzanie, które zostało określone za pomocą `atexit` funkcji.

## <a name="see-also"></a>Zobacz też

[Dodatkowe zagadnienia dotyczące kończenia](../cpp/additional-termination-considerations.md)

---
title: Użycie przerywania
ms.date: 11/04/2016
helpviewer_keywords:
- abort function
ms.assetid: 3ba39b78-ef74-4a8d-8dee-2d62442de174
ms.openlocfilehash: e8cc7bce552acf67c0f9bf2025e0040dc051cff6
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446425"
---
# <a name="using-abort"></a>Użycie przerywania

Wywołanie funkcji [Abort](../c-runtime-library/reference/abort.md) powoduje natychmiastowe zakończenie. Pomija proces normalnego niszczenia dla zainicjowanych globalnych obiektów statycznych. Pomija również specjalne przetwarzanie, które zostało określone przy użyciu funkcji `atexit`.

## <a name="see-also"></a>Zobacz też

[Dodatkowe zagadnienia dotyczące kończenia](../cpp/additional-termination-considerations.md)
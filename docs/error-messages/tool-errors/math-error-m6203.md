---
description: 'Dowiedz się więcej na temat: błąd matematyczny matematyczny m6203'
title: Błąd matematyczny M6203
ms.date: 11/04/2016
f1_keywords:
- M6203
helpviewer_keywords:
- M6203
ms.assetid: bd7fdd1c-83e4-4d6a-901e-10a0308bf5be
ms.openlocfilehash: fcb123af8c79b5ce839e13247f59cbbed42736f4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143874"
---
# <a name="math-error-m6203"></a>Błąd matematyczny M6203

"Function": błąd _OVERFLOW

Dany wynik funkcji był zbyt duży, aby można go było przedstawić.

Ten błąd wywołuje `_matherr` funkcję z nazwą funkcji, jej argumentami i typem błędu. Można napisać ponownie funkcję, `_matherr` Aby dostosować obsługę określonych błędów matematycznych zmiennoprzecinkowych w czasie wykonywania.

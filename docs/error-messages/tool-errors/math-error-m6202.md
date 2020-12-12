---
description: 'Dowiedz się więcej na temat: błąd matematyczny matematyczny m6202'
title: Błąd matematyczny M6202
ms.date: 11/04/2016
f1_keywords:
- M6202
helpviewer_keywords:
- M6202
ms.assetid: 4d17045f-c6dc-4705-9512-e9af12c35fb4
ms.openlocfilehash: f6d4c9c8abab59708854eaac6763181018f47473
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97244306"
---
# <a name="math-error-m6202"></a>Błąd matematyczny M6202

"Function": błąd _SING

Argument danej funkcji był wartością Singularity tej funkcji. Funkcja nie jest zdefiniowana dla tego argumentu.

Ten błąd wywołuje `_matherr` funkcję z nazwą funkcji, jej argumentami i typem błędu. Można napisać ponownie funkcję, `_matherr` Aby dostosować obsługę określonych błędów matematycznych zmiennoprzecinkowych w czasie wykonywania.

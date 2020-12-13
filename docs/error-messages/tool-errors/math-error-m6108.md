---
description: 'Dowiedz się więcej na temat: błąd matematyczny matematyczny m6108'
title: Błąd matematyczny M6108
ms.date: 11/04/2016
f1_keywords:
- M6108
helpviewer_keywords:
- M6108
ms.assetid: 054893b4-49bc-45d9-882f-7cb50ba387c0
ms.openlocfilehash: 1a0acf13bd166e499334cb13de33093c2c804f5f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143887"
---
# <a name="math-error-m6108"></a>Błąd matematyczny M6108

pierwiastek kwadratowy

Operand w operacji typu kwadratowego jest ujemny.

Program kończy pracę z kodem zakończenia 136.

> [!NOTE]
> `sqrt`Funkcja w bibliotece wykonawczej C i Pascal wewnętrzna funkcja **sqrt** nie generują tego błędu. Funkcja C `sqrt` sprawdza argument przed wykonaniem operacji i zwraca wartość błędu, jeśli operand jest ujemny. Funkcja Pascal **sqrt** GENERUJE błąd domeny [matematyczny M6201](../../error-messages/tool-errors/math-error-m6201.md) zamiast tego błędu.

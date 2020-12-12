---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4611'
title: Ostrzeżenie kompilatora (poziom 4) C4611
ms.date: 11/04/2016
f1_keywords:
- C4611
helpviewer_keywords:
- C4611
ms.assetid: bd90d0a6-75f9-4e97-968d-dda6773e9fd8
ms.openlocfilehash: df53392b2d56b9afb1ab0cbcb2fc7b6267d5f00f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97168270"
---
# <a name="compiler-warning-level-4-c4611"></a>Ostrzeżenie kompilatora (poziom 4) C4611

Interakcja między "funkcją" i zniszczeniem obiektu języka C++ nie jest przenośna

Na niektórych platformach funkcje, które obejmują, **`catch`** mogą nie obsługiwać semantyki obiektów w języku C++, gdy jest poza zakresem.

Aby uniknąć nieoczekiwanego zachowania, należy unikać używania **`catch`** w funkcjach, które mają konstruktory i destruktory.

To ostrzeżenie jest wysyłane tylko raz; Zobacz [pragma warning](../../preprocessor/warning.md).

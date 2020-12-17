---
description: Dowiedz się więcej o ostrzeżeniu kompilatora (poziom 1) C4027
title: Ostrzeżenie kompilatora (poziom 1) C4027
ms.date: 12/16/2020
f1_keywords:
- C4027
helpviewer_keywords:
- C4027
ms.openlocfilehash: 1489ca32211854bcf1ef55d1a4ac806ab1611f43
ms.sourcegitcommit: 387ce22a3b0137f99cbb856a772b5a910c9eba99
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/17/2020
ms.locfileid: "97645179"
---
# <a name="compiler-warning-level-1-c4027"></a>Ostrzeżenie kompilatora (poziom 1) C4027

> Funkcja zadeklarowana bez formalnej listy parametrów

Deklaracja funkcji nie ma formalnych parametrów, ale w definicji funkcji lub w parametrach rzeczywistych w wywołaniu nie ma parametrów formalnych.

Kompilator akceptuje, ale ostrzega, w starej deklaracji C-style do przodu nazwy funkcji bez listy parametrów. W przypadku późniejszego wywołania tej funkcji kompilator zakłada, że funkcja przyjmuje rzeczywiste parametry typów znalezionych w definicji funkcji lub wywołaniu. Zalecamy zmodyfikowanie deklaracji funkcji tak, aby była zgodna z sygnaturą definicji funkcji.

---
description: 'Dowiedz się więcej o: błąd kompilatora C3744'
title: Błąd kompilatora C3744
ms.date: 11/04/2016
f1_keywords:
- C3744
helpviewer_keywords:
- C3744
ms.assetid: a447d050-80d1-406a-9a6e-f15c527d717c
ms.openlocfilehash: 6d8e9184db37f65fd73a85aaaa6c350303802216
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340232"
---
# <a name="compiler-error-c3744"></a>Błąd kompilatora C3744

__unhook musi mieć co najmniej 3 argumenty dla zdarzeń zarządzanych

[`__unhook`](../../cpp/unhook.md)Funkcja musi przyjmować trzy parametry, gdy jest używany w programie kompilowanym dla Managed Extensions for C++.

**`__hook`** i **`__unhook`** nie są zgodne z **`/clr`** programowaniem. Zamiast tego użyj operatorów + = i-=.

C3744 jest osiągalna tylko przy użyciu przestarzałej opcji kompilatora **`/clr:oldSyntax`** .

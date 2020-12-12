---
description: 'Dowiedz się więcej o: błąd kompilatora C2708'
title: Błąd kompilatora C2708
ms.date: 11/04/2016
f1_keywords:
- C2708
helpviewer_keywords:
- C2708
ms.assetid: d52d3088-1141-42f4-829c-74755a7fcc3a
ms.openlocfilehash: c965375c92c98a58a0fb6d0d51b3358e6b5798b5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320873"
---
# <a name="compiler-error-c2708"></a>Błąd kompilatora C2708

"Identyfikator": rzeczywiste parametry długości w bajtach różnią się od poprzedniego wywołania lub odwołania

Funkcja [__stdcall](../../cpp/stdcall.md) musi być poprzedzona prototypem. W przeciwnym razie kompilator interpretuje pierwsze wywołanie funkcji jako prototyp i ten błąd występuje, gdy kompilator napotyka wywołanie, które nie jest zgodne.

Aby naprawić ten błąd, Dodaj prototyp funkcji.

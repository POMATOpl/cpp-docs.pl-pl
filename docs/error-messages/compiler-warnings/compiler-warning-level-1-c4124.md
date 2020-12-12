---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4124'
title: Ostrzeżenie kompilatora (poziom 1) C4124
ms.date: 11/04/2016
f1_keywords:
- C4124
helpviewer_keywords:
- C4124
ms.assetid: c08c3a65-9584-47a1-a147-44f00c4b230e
ms.openlocfilehash: 97fe65f8513f656d85059714ae598ffad9f7a49c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267394"
---
# <a name="compiler-warning-level-1-c4124"></a>Ostrzeżenie kompilatora (poziom 1) C4124

__fastcall ze sprawdzaniem stosu jest niewydajne

**`__fastcall`** Słowo kluczowe zostało użyte z włączonym sprawdzaniem stosu.

**`__fastcall`** Konwencja generuje szybszy kod, ale sprawdzanie stosu powoduje wolniejszy kod. W przypadku korzystania z programu Wyłącz **`__fastcall`** Sprawdzanie stosu przy użyciu **check_stack** pragma lub/GS.

To ostrzeżenie jest wydawane tylko dla pierwszej funkcji zadeklarowanej w tych warunkach.

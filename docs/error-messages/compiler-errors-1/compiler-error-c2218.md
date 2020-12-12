---
description: 'Dowiedz się więcej o: błąd kompilatora C2218'
title: Błąd kompilatora C2218
ms.date: 11/04/2016
f1_keywords:
- C2218
helpviewer_keywords:
- C2218
ms.assetid: b0f55da4-8edb-4b45-b298-1a091981bd7b
ms.openlocfilehash: d2761bb822c5a1055974e4a0bcd6011e7f451821
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245528"
---
# <a name="compiler-error-c2218"></a>Błąd kompilatora C2218

> nie można użyć "__vectorcall" z "/arch: IA32"

**`__vectorcall`** Konwencja wywoływania jest obsługiwana tylko w kodzie natywnym na procesorach x86 i x64, które zawierają Streaming SIMD Extensions 2 (SSE2) i nowsze. Aby uzyskać więcej informacji, zobacz [`__vectorcall`](../../cpp/vectorcall.md).

Aby naprawić ten błąd, Zmień opcje kompilatora w celu docelową SSE2, AVX lub AVX2 zestawów instrukcji. Aby uzyskać więcej informacji, zobacz [ `/arch` (x86)](../../build/reference/arch-x86.md).

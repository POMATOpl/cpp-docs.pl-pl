---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziomy 1 i 4) C4115'
title: Ostrzeżenie kompilatora (poziomy 1 i 4) C4115
ms.date: 11/04/2016
f1_keywords:
- C4115
helpviewer_keywords:
- C4115
ms.assetid: f3f94e72-fc49-4d09-b3e7-23d68e61152f
ms.openlocfilehash: f41dcdf16d541151384d50d004a55d6e1993ece0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234492"
---
# <a name="compiler-warning-levels-1-and-4-c4115"></a>Ostrzeżenie kompilatora (poziomy 1 i 4) C4115

"Type": nazwana definicja typu w nawiasach

Dany symbol jest używany do definiowania struktury, Unii lub typu wyliczeniowego wewnątrz wyrażenia ujętego w nawiasy. Zakres definicji może być nieoczekiwany.

W wywołaniu funkcji języka C definicja ma zakres globalny. W wywołaniu C++ definicja ma ten sam zakres co funkcja wywoływana.

To ostrzeżenie może być również spowodowane przez Deklaratory w nawiasach (takich jak prototypy), które nie są wyrażeniami w nawiasach.

Jest to ostrzeżenie poziomu 1 dotyczące programów C++ i programów C skompilowanych pod kątem zgodności ze standardem ANSI (/za). W przeciwnym razie jest to poziom 3.

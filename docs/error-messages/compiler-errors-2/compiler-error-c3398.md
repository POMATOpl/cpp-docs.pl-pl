---
description: 'Dowiedz się więcej o: błąd kompilatora C3398'
title: Błąd kompilatora C3398
ms.date: 11/04/2016
f1_keywords:
- C3398
helpviewer_keywords:
- C3398
ms.assetid: 26f8c8a4-526f-415b-8047-155c5cd4f180
ms.openlocfilehash: 024390ec03ad145f418f79d2db3228bd790a6de7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321944"
---
# <a name="compiler-error-c3398"></a>Błąd kompilatora C3398

"operator": nie można konwertować z "function_signature" na "function_pointer". Wyrażenie źródłowe musi być symbolem funkcji

Gdy nie określono konwencji wywoływania [__clrcall](../../cpp/clrcall.md) podczas kompilowania z **/CLR**, kompilator generuje dwa punkty wejścia (addresss) dla każdej funkcji, natywnego punktu wejścia i zarządzanego punktu wejścia.

Domyślnie kompilator zwraca natywny punkt wejścia, ale istnieją sytuacje, w których jest wymagany zarządzany punkt wejścia (na przykład podczas przypisywania adresu do `__clrcall` wskaźnika funkcji). Aby kompilator mógł niezawodnie wybrać zarządzany punkt wejścia w przypisaniu, po prawej stronie musi być symbolem funkcji.

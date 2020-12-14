---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4420'
title: Ostrzeżenie kompilatora (poziom 1) C4420
ms.date: 11/04/2016
f1_keywords:
- C4420
helpviewer_keywords:
- C4420
ms.assetid: 44a37754-7ddd-4764-a5f7-d33e05c20091
ms.openlocfilehash: 2a92d7296bf5c38655182e5c0dd2c200d0ccf42d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311074"
---
# <a name="compiler-warning-level-1-c4420"></a>Ostrzeżenie kompilatora (poziom 1) C4420

"operator": operator nie jest dostępny, przy użyciu "operator" zamiast; Sprawdzanie w czasie wykonywania może być naruszone

To ostrzeżenie jest generowane, gdy używasz [/RTCv](../../build/reference/rtc-run-time-error-checks.md) (sprawdzanie nowego/usuwania wektora) i gdy nie zostanie znaleziony żaden formularz wektorowy. W tym przypadku jest używany formularz niebędący wektorem.

Aby/RTCv działał prawidłowo, kompilator powinien zawsze wywołać formę Vector dla [nowego](../../cpp/new-operator-cpp.md) / [usunięcia](../../cpp/delete-operator-cpp.md) , jeśli użyto składni wektorowej.

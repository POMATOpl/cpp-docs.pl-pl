---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4799'
title: Ostrzeżenie kompilatora (poziom 1) C4799
ms.date: 11/04/2016
f1_keywords:
- C4799
helpviewer_keywords:
- C4799
ms.assetid: 8ecbd06f-c778-4371-a2fb-c690b6743ec8
ms.openlocfilehash: 9bfa84791a713d5ed5c0382402b958c255e30521
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334940"
---
# <a name="compiler-warning-level-1-c4799"></a>Ostrzeżenie kompilatora (poziom 1) C4799

> Brak EMMS na końcu funkcji "*Function*"

Funkcja ma co najmniej jedną instrukcję MMX, ale nie ma `EMMS` instrukcji. Gdy jest używana instrukcja multimedialna, `EMMS` instrukcja lub `_mm_empty` wewnętrzna powinna również służyć do czyszczenia słowa tag multimedialny na końcu kodu MMX.

Użytkownik może uzyskać C4799 podczas korzystania z ivec. h, wskazując, że kod nie używa prawidłowo instrukcji EMMS przed zwróceniem. Jest to fałszywe ostrzeżenie dla tych nagłówków. Można je wyłączyć przez zdefiniowanie _SILENCE_IVEC_C4799 w IVEC. h. Należy jednak pamiętać, że spowoduje to również zachowanie przez kompilator prawidłowych ostrzeżeń tego typu.

Aby uzyskać powiązane informacje, zobacz [zestaw instrukcji MMX firmy Intel](../../assembler/inline/intel-s-mmx-instruction-set.md).

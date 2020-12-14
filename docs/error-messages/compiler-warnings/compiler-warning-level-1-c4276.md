---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4276'
title: Ostrzeżenie kompilatora (poziom 1) C4276
ms.date: 11/04/2016
f1_keywords:
- C4276
helpviewer_keywords:
- C4276
ms.assetid: 9d738c2d-29e5-408a-b9ff-be1a850b2238
ms.openlocfilehash: 14b13b2eb1e13d28f2b208e52ef71e1c729fe5e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311789"
---
# <a name="compiler-warning-level-1-c4276"></a>Ostrzeżenie kompilatora (poziom 1) C4276

"Function": nie dostarczono prototypu; przyjęto, że nie ma parametrów

Gdy przyjmujesz adres funkcji z konwencją wywoływania [__stdcall](../../cpp/stdcall.md) , musisz nadać prototyp, aby kompilator mógł utworzyć nazwę dekoracyjną funkcji. Ponieważ *Funkcja* nie ma prototypu, kompilator, podczas tworzenia nazwy dekoracyjnej, zakłada, że funkcja nie ma parametrów.

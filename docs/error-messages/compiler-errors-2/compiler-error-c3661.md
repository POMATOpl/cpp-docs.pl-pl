---
description: 'Dowiedz się więcej o: błąd kompilatora C3661'
title: Błąd kompilatora C3661
ms.date: 11/04/2016
f1_keywords:
- C3661
helpviewer_keywords:
- C3661
ms.assetid: 50793fd1-1829-4b29-ad0d-094ef2068b43
ms.openlocfilehash: f8b0321b98d9f9fd89de926532177b9a000d2ce2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134319"
---
# <a name="compiler-error-c3661"></a>Błąd kompilatora C3661

Lista jawnego przesłaniania nie znalazła żadnych metod do przesłonięcia

Jawne przesłonięcie określiło jedną lub więcej nazw typów.  Jednak w typach, które pasują do sygnatury funkcji przesłaniania, nie było żadnej funkcji z niezbędnym podpisem.  Jeśli próbujesz przesłonić na podstawie nazwy typu, musi istnieć co najmniej jedna funkcja wirtualna w określonych typach, która pasuje do sygnatury funkcji zastępującej.

Aby uzyskać więcej informacji, zobacz [jawne zastąpienia](../../extensions/explicit-overrides-cpp-component-extensions.md).

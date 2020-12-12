---
description: 'Dowiedz się więcej o: błąd kompilatora C2919'
title: Błąd kompilatora C2919
ms.date: 11/04/2016
f1_keywords:
- C2919
helpviewer_keywords:
- C2919
ms.assetid: 140a6db9-eb48-4c5e-84a7-a09d2653605b
ms.openlocfilehash: 0e6498961fc5000897bcd9815c3cd3a6f90ecdfb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270345"
---
# <a name="compiler-error-c2919"></a>Błąd kompilatora C2919

"Type": nie można używać operatorów na publikowanej powierzchni typu WinRT

System typu środowisko wykonawcze systemu Windows nie obsługuje funkcji składowych operatorów na publikowanej powierzchni typu. Wynika to z faktu, że nie wszystkie języki mogą korzystać z funkcji Członkowskich operatora. Można tworzyć funkcje składowe operatora prywatnego lub wewnętrznego, które mogą być wywoływane z kodu C++ w tej samej klasie lub jednostce kompilacji.

Aby rozwiązać ten problem, Usuń funkcję członkowską operatora z interfejsu publicznego lub Zmień ją na nazwę funkcji członkowskiej. Na przykład zamiast `operator==` nazwy funkcji składowej `Equals` .

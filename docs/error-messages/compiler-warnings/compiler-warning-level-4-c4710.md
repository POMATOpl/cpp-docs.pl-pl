---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4710'
title: Ostrzeżenie kompilatora (poziom 4) C4710
ms.date: 11/04/2016
f1_keywords:
- C4710
helpviewer_keywords:
- C4710
ms.assetid: 76381ec7-3fc1-4bee-9a0a-c2c8307b92e2
ms.openlocfilehash: b10a2add132335db48c49ae69740d04f792f126e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330586"
---
# <a name="compiler-warning-level-4-c4710"></a>Ostrzeżenie kompilatora (poziom 4) C4710

"Function": funkcja nie została wbudowana

Dana funkcja została wybrana do rozwijania wbudowanego, ale kompilator nie przeprowadził tworzenia konspektu.

Tworzenie i składanie jest wykonywane według uznania kompilatora. **`inline`** Słowo kluczowe, takie jak **`register`** słowo kluczowe, jest używane jako Wskazówka dla kompilatora. Kompilator używa algorytmów heurystycznych, aby określić, czy powinien on być wbudowany w konkretną funkcję w celu przyspieszenia kodu podczas kompilowania do szybkości, czy też powinien być wbudowany w konkretną funkcję, aby zmniejszyć kod podczas kompilowania do miejsca. Kompilator będzie tylko wbudowanych bardzo małych funkcji podczas kompilowania do miejsca.

W niektórych przypadkach kompilator nie będzie wbudowanej określonej funkcji dla powodów mechanicznych. Zobacz [C4714](../../error-messages/compiler-warnings/compiler-warning-level-4-c4714.md) , aby zapoznać się z listą przyczyn, które kompilator nie może zawbudowanić funkcji.

To ostrzeżenie jest domyślnie wyłączone. Aby uzyskać więcej informacji [, zobacz ostrzeżenia kompilatora, które są domyślnie wyłączone](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

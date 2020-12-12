---
description: 'Dowiedz się więcej o: błąd kompilatora C2129'
title: Błąd kompilatora C2129
ms.date: 11/04/2016
f1_keywords:
- C2129
helpviewer_keywords:
- C2129
ms.assetid: 21a8223e-1d22-4baa-9ca1-922b7f751dd0
ms.openlocfilehash: 5efb19aa3f4edd14dd6cfab93c3880745b08e59d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323158"
---
# <a name="compiler-error-c2129"></a>Błąd kompilatora C2129

funkcja statyczna "Function" została zadeklarowana, ale nie została zdefiniowana

Odwołanie do przodu jest tworzone do **`static`** funkcji, która nigdy nie jest zdefiniowana.

**`static`** Funkcja musi być zdefiniowana w zakresie pliku. Jeśli funkcja jest zdefiniowana w innym pliku, musi być zadeklarowana **`extern`** .

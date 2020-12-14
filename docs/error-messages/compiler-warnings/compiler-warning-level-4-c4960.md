---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4960'
title: Ostrzeżenie kompilatora (poziom 4) C4960
ms.date: 11/04/2016
f1_keywords:
- C4960
helpviewer_keywords:
- C4960
ms.assetid: 3b4ed286-9e8d-46f1-af0c-00ba669693a9
ms.openlocfilehash: 9a1e3d5390ffa4ffad101d1ea2c3164c04d12ca8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234582"
---
# <a name="compiler-warning-level-4-c4960"></a>Ostrzeżenie kompilatora (poziom 4) C4960

element "Function" jest zbyt duży, aby można go było profilować

W przypadku korzystania z [/LTCG: PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md)Kompilator wykrył Moduł wejściowy z funkcją przekraczającą 65 535 instrukcji. Taka duża funkcja nie jest dostępna w przypadku optymalizacji z przewodnikiem.

Aby usunąć to ostrzeżenie, zmniejsz rozmiar funkcji.

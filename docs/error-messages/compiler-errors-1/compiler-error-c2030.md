---
description: 'Dowiedz się więcej o: błąd kompilatora C2030'
title: Błąd kompilatora C2030
ms.date: 11/04/2016
f1_keywords:
- C2030
helpviewer_keywords:
- C2030
ms.assetid: 5806cead-64df-4eff-92de-52c9a3f5ee62
ms.openlocfilehash: b29996051a87f050e61c94b4134d046f52be6f09
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175485"
---
# <a name="compiler-error-c2030"></a>Błąd kompilatora C2030

destruktor z ułatwieniami dostępu "protected private" nie może być składową klasy zadeklarowanej jako "Sealed"

Klasa środowisko wykonawcze systemu Windows zadeklarowana jako **`sealed`** nie może mieć chronionego destruktora prywatnego. Tylko publiczne wirtualne i prywatne destruktory niewirtualne są dozwolone w typach zapieczętowanych. Aby uzyskać więcej informacji, zobacz [klasy referencyjne i struktury](../../cppcx/ref-classes-and-structs-c-cx.md).

Aby naprawić ten błąd, Zmień dostępność destruktora.

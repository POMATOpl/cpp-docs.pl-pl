---
description: 'Dowiedz się więcej na temat: Optymalizacja wbudowanego zestawu'
title: Optymalizacja wbudowanego asemblera
ms.date: 08/30/2018
helpviewer_keywords:
- storage, optimizing in inline assembly
- optimization, inline assembly
- inline assembly, optimizing
- optimizing performance, inline assembly
- __asm keyword [C++], optimizing
ms.assetid: 52a7ec83-9782-4d96-94c1-53bb2ac9e8c8
ms.openlocfilehash: 62c4dad85128089cdcf85f4156884747f928338f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122099"
---
# <a name="optimizing-inline-assembly"></a>Optymalizacja wbudowanego asemblera

**Specyficzne dla firmy Microsoft**

Obecność **`__asm`** bloku w funkcji ma wpływ na optymalizację na kilka sposobów. Najpierw kompilator nie próbuje zoptymalizować **`__asm`** samego bloku. To, co otrzymujesz w języku asemblera, jest dokładne. Po drugie, obecność **`__asm`** bloku ma wpływ na rejestr magazynu zmiennych. Kompilator pozwala uniknąć zmiennych rejestrowanie w bloku, **`__asm`** Jeśli zawartość rejestru zostałaby zmieniona przez **`__asm`** blok. Na koniec niektóre inne optymalizacje na poziomie funkcji mają wpływ na włączenie języka zestawu w funkcji.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Asembler wbudowany](../../assembler/inline/inline-assembler.md)<br/>

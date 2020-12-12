---
description: 'Dowiedz się więcej o: błąd niekrytyczny ML A2066'
title: Błąd niekrytyczny ML A2066
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A2066
helpviewer_keywords:
- A2066
ms.assetid: 58220fdf-fb8f-47fc-a36d-737867361185
ms.openlocfilehash: 703244bde7b55a5e109352a3e51a0b4402829242
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97128755"
---
# <a name="ml-nonfatal-error-a2066"></a>Błąd niekrytyczny ML A2066

**niezgodny tryb procesora CPU i rozmiar segmentu**

Podjęto próbę otwarcia segmentu z atrybutem **USE16**, **USE32** lub **flatem** , który nie jest zgodny z określonym procesorem CPU, lub aby zmienić na 16-bitowy procesor w ramach segmentu 32-bitowego.

Atrybuty **USE32** i **Flat** muszą być poprzedzone dyrektywą procesora. 386 lub większą.

## <a name="see-also"></a>Zobacz też

[Komunikaty o błędach ML](ml-error-messages.md)

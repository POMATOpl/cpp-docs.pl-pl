---
description: 'Dowiedz się więcej o: pierwszeństwo w definicjach makr'
title: Pierwszeństwo w definicjach makr
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, precedence in macro definitions
- macros, precedence
ms.assetid: 0c13182d-83cb-4cbd-af2d-f4c916b62aeb
ms.openlocfilehash: 1738c4ba77f330103395278a6daae169b04fae4c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225898"
---
# <a name="precedence-in-macro-definitions"></a>Pierwszeństwo w definicjach makr

Jeśli makro ma wiele definicji, NMAKE używa definicji o najwyższej priorytecie. Na poniższej liście przedstawiono kolejność pierwszeństwa, od najwyższego do najniższego:

1. Makro zdefiniowane w wierszu polecenia

1. Makro zdefiniowane w pliku reguł programu make lub plików dołączanych

1. Dziedziczone makro zmienna środowiskowa

1. Makro zdefiniowane w pliku Tools.ini

1. Wstępnie zdefiniowane makro, takie jak [CC](command-macros-and-options-macros.md) i [as](command-macros-and-options-macros.md)

Użyj/E, aby spowodować, że makra dziedziczone ze zmiennych środowiskowych przesłaniają makra pliku reguł programu make o tej samej nazwie. Użyj **! UNDEF** , aby zastąpić wiersz polecenia.

## <a name="see-also"></a>Zobacz też

[Definiowanie makra NMAKE](defining-an-nmake-macro.md)

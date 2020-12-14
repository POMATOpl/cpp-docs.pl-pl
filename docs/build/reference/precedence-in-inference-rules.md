---
description: 'Dowiedz się więcej o: pierwszeństwo w regułach wnioskowania'
title: Pierwszeństwo w zasadach wnioskowania
ms.date: 11/04/2016
helpviewer_keywords:
- inference rules in NMAKE
- rules, inference
- precedence, inference rule
ms.assetid: 69e3dc02-0815-4c3a-b02b-1cb85fceaf24
ms.openlocfilehash: b56d01cce63aaaac92e011630e45bcf43e7fe0b3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225911"
---
# <a name="precedence-in-inference-rules"></a>Pierwszeństwo w zasadach wnioskowania

Jeśli reguła wnioskowania jest zdefiniowana wielokrotnie, NMAKE używa definicji o najwyższej priorytecie. Na poniższej liście przedstawiono kolejność pierwszeństwa od najwyższego do najniższego:

1. Reguła wnioskowania zdefiniowana w pliku reguł programu make; nowsze definicje mają pierwszeństwo.

1. Reguła wnioskowania zdefiniowana w Tools.ini; nowsze definicje mają pierwszeństwo.

1. Wstępnie zdefiniowana reguła wnioskowania.

## <a name="see-also"></a>Zobacz też

[Zasady wnioskowania](inference-rules.md)

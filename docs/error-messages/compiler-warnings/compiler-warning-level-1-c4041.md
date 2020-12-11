---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4041'
title: Ostrzeżenie kompilatora (poziom 1) C4041
ms.date: 11/04/2016
f1_keywords:
- C4041
helpviewer_keywords:
- C4041
ms.assetid: 107ee9fd-4b88-4f22-a18f-a20726831095
ms.openlocfilehash: d3473be35182f6c99541aa2a0fc79de79dee4a07
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97160717"
---
# <a name="compiler-warning-level-1-c4041"></a>Ostrzeżenie kompilatora (poziom 1) C4041

ograniczenie kompilatora: Trwa kończenie wyświetlania wyników przeglądarki

Informacje o przeglądarce przekraczają limit kompilatora.

To ostrzeżenie może być spowodowane kompilacją z [/fr](../../build/reference/fr-fr-create-dot-sbr-file.md) (informacje o przeglądarce, w tym zmienne lokalne).

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aby rozwiązać ten problem, można użyć następujących rozwiązań

1. Kompiluj z/fr (informacje o przeglądarce bez zmiennych lokalnych).

1. Wyłącz dane wyjściowe przeglądarki (Kompiluj bez/FR lub/fr).

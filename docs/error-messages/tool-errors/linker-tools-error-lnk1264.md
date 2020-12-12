---
description: 'Dowiedz się więcej na temat: Błąd narzędzi konsolidatora LNK1264'
title: Błąd narzędzi konsolidatora LNK1264
ms.date: 11/04/2016
f1_keywords:
- LNK1264
helpviewer_keywords:
- LNK1264
ms.assetid: 23b1aad7-d382-42c1-bae8-db68575c57a8
ms.openlocfilehash: 122186482800597780405ae89e8e01c008794756
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193789"
---
# <a name="linker-tools-error-lnk1264"></a>Błąd narzędzi konsolidatora LNK1264

/LTCG: PGINSTRUMENT określony, ale nie jest wymagane generowanie kodu; Instrumentacja nie powiodła się

**/LTCG: PGINSTRUMENT** został określony, ale nie znaleziono plików. obj, które zostały skompilowane z [/GL](../../build/reference/gl-whole-program-optimization.md). Nie można przeprowadzić instrumentacji, a łącze nie powiodło się. W wierszu polecenia, który jest kompilowany za pomocą **/GL** , musi istnieć co najmniej jeden plik. obj, dzięki czemu może wystąpić Instrumentacja.

Optymalizacja profilowana (PGO) jest dostępna tylko w kompilatorach 64-bitowych.

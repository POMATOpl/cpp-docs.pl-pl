---
description: 'Dowiedz się więcej na temat: _CRTDBG_MAP_ALLOC'
title: _CRTDBG_MAP_ALLOC
ms.date: 11/04/2016
f1_keywords:
- CRTDBG_MAP_ALLOC
- _CRTDBG_MAP_ALLOC
helpviewer_keywords:
- _CRTDBG_MAP_ALLOC macro
- memory allocation, in debug builds
- CRTDBG_MAP_ALLOC macro
ms.assetid: 435242b8-caea-4063-b765-4a608200312b
ms.openlocfilehash: e2747f6da04c019b551e68c78f6f1448c48093f1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224273"
---
# <a name="_crtdbg_map_alloc"></a>_CRTDBG_MAP_ALLOC

Gdy flaga **_CRTDBG_MAP_ALLOC** jest zdefiniowana w wersji debugowej aplikacji, wersja podstawowa funkcji sterty jest bezpośrednio mapowana na ich wersje debugowania. Flaga jest używana w CRTDBG. h do wykonania mapowania. Ta flaga jest dostępna tylko wtedy, gdy flaga [_DEBUG](../c-runtime-library/debug.md) została zdefiniowana w aplikacji.

Aby uzyskać więcej informacji na temat używania wersji debugowania w porównaniu z wersją podstawową funkcji sterty, zobacz [Używanie wersji debugowania w porównaniu z wersją bazową](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="see-also"></a>Zobacz też

[Flagi kontrolki](../c-runtime-library/control-flags.md)

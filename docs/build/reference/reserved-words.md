---
description: 'Dowiedz się więcej o: słowa zastrzeżone'
title: Słowa zastrzeżone
ms.date: 11/04/2016
f1_keywords:
- code
- CONFORMING
- DISCARDABLE
- Description
- base
- APPLOADER
- Data
- DYNAMIC
- DEV386
helpviewer_keywords:
- .def files [C++], reserved words
- def files [C++], reserved words
- linker [C++], reserved words
- reserved words [C++]
ms.assetid: 9b9f49e5-0739-45ab-a37e-81e3915ceb25
ms.openlocfilehash: 6d5c5971d8d01dffa1dcd1e7f6a5228fb239d4dc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225196"
---
# <a name="reserved-words"></a>Słowa zastrzeżone

Następujące słowa są zastrzeżone przez konsolidator. Te nazwy mogą być używane jako argumenty w [instrukcjach definicji modułów](module-definition-dot-def-files.md) tylko wtedy, gdy nazwa jest ujęta w znaki podwójnego cudzysłowu ("").

:::row:::
   :::column span="":::
      **`APPLOADER`**<sup>jedno</sup>\
      **`BASE`**\
      **`CODE`**\
      **`CONFORMING`**\
      **`DATA`**\
      **`DESCRIPTION`**\
      **`DEV386`**\
      **`DISCARDABLE`**\
      **`DYNAMIC`**\
      **`EXECUTE-ONLY`**\
      **`EXECUTEONLY`**\
      **`EXECUTEREAD`**\
      **`EXETYPE`**\
      **`EXPORTS`**\
      **`FIXED`**<sup>jedno</sup>
   :::column-end:::
   :::column span="":::
      **`FUNCTIONS`**<sup>dwóch</sup>\
      **`HEAPSIZE`**\
      **`IMPORTS`**\
      **`IMPURE`**<sup>jedno</sup>\
      **`INCLUDE`**<sup>dwóch</sup>\
      **`INITINSTANCE`**<sup>dwóch</sup>\
      **`IOPL`**\
      **`LIBRARY`**<sup>jedno</sup>\
      **`LOADONCALL`**<sup>jedno</sup>\
      **`LONGNAMES`**<sup>dwóch</sup>\
      **`MOVABLE`**<sup>jedno</sup>\
      **`MOVEABLE`**<sup>jedno</sup>\
      **`MULTIPLE`**\
      **`NAME`**\
      **`NEWFILES`**<sup>dwóch</sup>
   :::column-end:::
   :::column span="":::
      **`NODATA`**<sup>jedno</sup>\
      **`NOIOPL`**<sup>jedno</sup>\
      **`NONAME`**\
      **`NONCONFORMING`**<sup>jedno</sup>\
      **`NONDISCARDABLE`**\
      **`NONE`**\
      **`NONSHARED`**\
      **`NOTWINDOWCOMPAT`**<sup>jedno</sup>\
      **`OBJECTS`**\
      **`OLD`**<sup>jedno</sup>\
      **`PRELOAD`**\
      **`PRIVATE`**\
      **`PROTMODE`**<sup>dwóch</sup>\
      **`PURE`**<sup>jedno</sup>\
      **`READONLY`**
   :::column-end:::
   :::column span="":::
      **`READWRITE`**\
      **`REALMODE`**<sup>jedno</sup>\
      **`RESIDENT`**\
      **`RESIDENTNAME`**<sup>jedno</sup>\
      **`SECTIONS`**\
      **`SEGMENTS`**\
      **`SHARED`**\
      **`SINGLE`**\
      **`STACKSIZE`**\
      **`STUB`**\
      **`VERSION`**\
      **`WINDOWAPI`**\
      **`WINDOWCOMPAT`**\
      **`WINDOWS`**
   :::column-end:::
:::row-end:::

<sup>1</sup> konsolidator emituje ostrzeżenie ("zignorowano") w momencie napotkania tego terminu. Jednak słowo jest nadal zarezerwowane.

<sup>2</sup> konsolidator ignoruje ten wyraz, ale nie emituje ostrzeżenia.

## <a name="see-also"></a>Zobacz też

- [Dokumentacja konsolidatora MSVC](linking.md)
- [MSVC Opcje konsolidatora](linker-options.md)

---
description: 'Dowiedz się więcej o: podpisane operacje bitowe'
title: Operacje bitowe ze znakiem
ms.date: 11/04/2016
helpviewer_keywords:
- bitwise operations
- signed bitwise operations
ms.assetid: 1e5cf65b-ee32-41a0-a5c2-82c1854091f6
ms.openlocfilehash: 98cca4d7450e0b65301ba3d2ad65f0cb3aca81ea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97292653"
---
# <a name="signed-bitwise-operations"></a>Operacje bitowe ze znakiem

**ANSI 3,3** Wyniki operacji bitowych w przypadku liczb całkowitych ze znakiem

Operacje bitowe w podpisanych liczbach całkowitych działają tak samo jak operacje bitowe w liczbach całkowitych bez znaku. Na przykład `-16 & 99` może być wyrażona jako plik binarny jako

```
  11111111 11110000
& 00000000 01100011
  _________________
  00000000 01100000
```

Wynik bitowy jest 96.

## <a name="see-also"></a>Zobacz też

[Liczby całkowite](../c-language/integers.md)

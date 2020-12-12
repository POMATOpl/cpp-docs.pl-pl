---
description: 'Dowiedz się więcej o: błąd kompilatora C3415'
title: Błąd kompilatora C3415
ms.date: 11/04/2016
f1_keywords:
- C3415
helpviewer_keywords:
- C3415
ms.assetid: fa2db8ab-2820-4ec3-a740-fb5e2adcfb29
ms.openlocfilehash: 3f50f2bd7a443c01f820aa1915f14d83e0b0dbe8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321916"
---
# <a name="compiler-error-c3415"></a>Błąd kompilatora C3415

znaleziono wiele sekcji "section_name" z różnymi atrybutami ("value")

W [sekcjach](../../preprocessor/section.md) pragma określono wartości powodujące konflikt.

`value` jest bieżącym ustawieniem dla sekcji, jak określono w ntimage. h. Na przykład:

```
// Section contains extended relocations.
#define IMAGE_SCN_LNK_NRELOC_OVFL            0x01000000
// Section can be discarded.
#define IMAGE_SCN_MEM_DISCARDABLE            0x02000000
// Section is not cachable.
#define IMAGE_SCN_MEM_NOT_CACHED             0x04000000
// Section is not pageable.
#define IMAGE_SCN_MEM_NOT_PAGED              0x08000000
// Section is shareable.
#define IMAGE_SCN_MEM_SHARED                 0x10000000
// Section is executable.
#define IMAGE_SCN_MEM_EXECUTE                0x20000000
// Section is readable.
#define IMAGE_SCN_MEM_READ                   0x40000000
// Section is writeable.
#define IMAGE_SCN_MEM_WRITE                  0x80000000
```

Poniższy przykład generuje C3415:

```cpp
// C3415.cpp
#pragma section("mysec1",write)
#pragma section("mysec1",read)   // C3415
```

---
description: 'Dowiedz się więcej o zarządzaniu pamięcią: bloki pamięci o zmiennym rozmiarze'
title: 'Zarządzanie pamięcią: bloki pamięci o zmiennych rozmiarach'
ms.date: 11/04/2016
helpviewer_keywords:
- memory blocks [MFC], resizable
- memory [MFC], corruption
- memory allocation [MFC], memory block size
- memory blocks [MFC], allocating
- blocks [MFC], memory allocation
- resizable memory blocks [MFC]
ms.assetid: f0efe6f4-a3ed-4541-9195-51ec1291967a
ms.openlocfilehash: bcca5617a0d59a7dd5c6a1f9c9f82cb5876f1ef5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248882"
---
# <a name="memory-management-resizable-memory-blocks"></a>Zarządzanie pamięcią: bloki pamięci o zmiennych rozmiarach

**`new`** Operatory i **`delete`** , opisane w temacie [Zarządzanie pamięcią artykułu: przykłady](memory-management-examples.md), są przydatne do przydzielania i cofania przydziału bloków pamięci o ustalonym rozmiarze i obiektów. Czasami aplikacja może potrzebować bloków pamięci o zmiennym rozmiarze. Aby zarządzać blokami pamięci o zmiennym rozmiarze na stercie, należy użyć standardowej biblioteki wykonawczej C funkcji [malloc](../c-runtime-library/reference/malloc.md), [realloc](../c-runtime-library/reference/realloc.md)i [Free](../c-runtime-library/reference/free.md) .

> [!IMPORTANT]
> Mieszanie **`new`** operatorów i **`delete`** o zmiennym rozmiarze alokacji pamięci w tym samym bloku pamięci spowoduje uszkodzenie pamięci w debugowanej wersji biblioteki MFC. Nie należy używać **realloc** w bloku pamięci przydzielonym za pomocą **`new`** . Podobnie nie należy przydzielać bloku pamięci z **`new`** operatorem i usuwać go z opcją **Free** ani używać **`delete`** operatora w bloku pamięci przydzielonej za pomocą funkcji **malloc**.

## <a name="see-also"></a>Zobacz też

[Zarządzanie pamięcią: Alokacja sterty](memory-management-heap-allocation.md)

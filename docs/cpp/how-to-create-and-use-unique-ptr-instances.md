---
description: 'Dowiedz się więcej na temat: Instrukcje: Tworzenie wystąpień unique_ptr i korzystanie z nich'
title: 'Instrukcje: Tworzenie wystąpień unique_ptr i korzystanie z nich'
ms.custom: how-to
ms.date: 11/19/2018
ms.topic: conceptual
ms.assetid: 9a373030-e587-452f-b9a5-c5f9d58b7673
ms.openlocfilehash: a53b3a9704c62803b50c9bde2c7db70c190a8008
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97268668"
---
# <a name="how-to-create-and-use-unique_ptr-instances"></a>Instrukcje: Tworzenie wystąpień unique_ptr i korzystanie z nich

[Unique_ptr](../standard-library/unique-ptr-class.md) nie udostępnia swojego wskaźnika. Nie można go skopiować do innego `unique_ptr` , przekazywać przez wartość do funkcji ani używać w żadnym algorytmie standardowej biblioteki języka C++, który wymaga dokonania kopii. `unique_ptr`Można przenieść tylko. Oznacza to, że własność zasobu pamięci jest przenoszona do innego `unique_ptr` , a oryginał `unique_ptr` nie jest już właścicielem. Zalecamy, aby ograniczyć obiekt do jednego właściciela, ponieważ wiele własności zwiększa złożoność logiki programu. W związku z tym, jeśli potrzebujesz inteligentnego wskaźnika dla zwykłego obiektu języka C++, użyj `unique_ptr` , a podczas konstruowania `unique_ptr` Użyj funkcji pomocnika [make_unique](../standard-library/memory-functions.md#make_unique) .

Na poniższym diagramie przedstawiono przeniesienie własności między dwoma `unique_ptr` wystąpieniami.

![Przeniesienie własności unikatowego&#95;PTR](media/unique_ptr.png "Przeniesienie własności unikatowego&#95;PTR")

`unique_ptr` jest zdefiniowany w `<memory>` nagłówku w standardowej bibliotece języka C++. Jest on dokładnie tak wydajny jak wskaźnik surowy i może być używany w kontenerach standardowej biblioteki języka C++. Dodawanie `unique_ptr` wystąpień do kontenerów standardowej biblioteki C++ jest wydajne, ponieważ Konstruktor przenoszenia dla `unique_ptr` eliminuje potrzebę operacji kopiowania.

## <a name="example-1"></a>Przykład 1

Poniższy przykład pokazuje, jak tworzyć `unique_ptr` wystąpienia i przekazywać je między funkcjami.

[!code-cpp[stl_smart_pointers#210](codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_1.cpp)]

Te przykłady przedstawiają tę podstawową cechę `unique_ptr` : można ją przenieść, ale nie kopiować. "Przenoszenie" przenosi własność do nowego `unique_ptr` i resetuje stary `unique_ptr` .

## <a name="example-2"></a>Przykład 2

Poniższy przykład pokazuje, jak tworzyć `unique_ptr` wystąpienia i korzystać z nich w wektorze.

[!code-cpp[stl_smart_pointers#211](codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_2.cpp)]

Zwróć uwagę, że element `unique_ptr` jest przekazywany przez odwołanie do zakresu pętli. Jeśli spróbujesz przekazać wartość tutaj, kompilator zgłosi błąd, ponieważ `unique_ptr` Konstruktor kopiujący został usunięty.

## <a name="example-3"></a>Przykład 3

Poniższy przykład pokazuje, jak zainicjować element `unique_ptr` członkowski klasy.

[!code-cpp[stl_smart_pointers#212](codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_3.cpp)]

## <a name="example-4"></a>Przykład 4

Możesz użyć [make_unique](../standard-library/memory-functions.md#make_unique) , aby utworzyć `unique_ptr` tablicę, ale nie można użyć, `make_unique` Aby zainicjować elementy tablicy.

[!code-cpp[stl_smart_pointers#213](codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_4.cpp)]

Aby uzyskać więcej przykładów, zobacz [make_unique](../standard-library/memory-functions.md#make_unique).

## <a name="see-also"></a>Zobacz też

[Inteligentne wskaźniki (nowoczesne C++)](smart-pointers-modern-cpp.md)<br/>
[make_unique](../standard-library/memory-functions.md#make_unique)

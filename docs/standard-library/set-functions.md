---
description: 'Dowiedz się więcej na temat: &lt; Ustawianie &gt; funkcji'
title: '&lt;Ustaw &gt; funkcje'
ms.date: 11/04/2016
f1_keywords:
- set/std::swap (map)
- set/std::swap (multiset)
ms.assetid: d1277d14-8502-46c0-b820-bcda820f9406
ms.openlocfilehash: 14f8eac3f725f88d98cdba133dace06993e5c089
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154139"
---
# <a name="ltsetgt-functions"></a>&lt;Ustaw &gt; funkcje

## <a name="swap-map"></a><a name="swap"></a> Zamień (mapa)

Zamienia elementy z dwóch zestawów.

```cpp
template <class Key, class Traits, class Allocator>
void swap(set<Key, Traits, Allocator>& left, set<Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametry

*Kliknij*\
Zestaw udostępniający elementy, które mają zostać zamienione lub zestaw, którego elementy mają być wymieniane z tymi z zestawu *po lewej stronie*.

*lewym*\
Zestaw, którego elementy mają być wymieniane z tymi zestawami *po prawej stronie*.

### <a name="remarks"></a>Uwagi

Funkcja szablonu jest algorytmem wyspecjalizowanym dla klasy kontenera ustawioną do wykonywania operacji swap funkcji składowej `left.` [](../standard-library/set-class.md#swap)( `right` ). Jest to wystąpienie częściowego porządkowania szablonów funkcji przez kompilator. Gdy funkcje szablonu są przeciążone w taki sposób, że dopasowanie szablonu z wywołaniem funkcji nie jest unikatowe, kompilator wybierze najbardziej wyspecjalizowaną wersję funkcji szablonu. Ogólna wersja funkcji szablonu

`template`\< **classT**> **void swap**( **t&**, **t&**)

w klasie algorytmu działa przez przypisanie i jest operacją powolnej. Wyspecjalizowana wersja w każdym kontenerze jest znacznie szybsza, ponieważ może pracować z wewnętrzną reprezentacją klasy Container.

### <a name="example"></a>Przykład

Zobacz przykład kodu dla zestawu klasy składowej [:: swap](../standard-library/set-class.md#swap) dla przykładu użycia wersji szablonu `swap` .

## <a name="swap-multiset"></a><a name="swap_multiset"></a> swap (zestaw wielokrotny)

Wymienia elementy dwóch zestawów wielozbiorówowych.

```cpp
template <class Key, class Traits, class Allocator>
void swap(multiset<Key, Traits, Allocator>& left, multiset<Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametry

*Kliknij*\
Zestaw *wielokrotny* udostępniający elementy, które mają zostać zamienione, lub zestaw wielokrotny, którego elementy mają być wymieniane z tymi z zestawu wielokrotnego.

*lewym*\
Zestaw *wielokrotny*, którego elementy mają być wymieniane z tymi samymi zestawem wielokrotnym.

### <a name="remarks"></a>Uwagi

Funkcja szablonu jest algorytmem wyspecjalizowanym dla zestawu wielokrotnego klasy kontenera do wykonywania operacji swap funkcji składowej `left.` [](../standard-library/multiset-class.md#swap)( `right` ). Jest to wystąpienie częściowego porządkowania szablonów funkcji przez kompilator. Gdy funkcje szablonu są przeciążone w taki sposób, że dopasowanie szablonu z wywołaniem funkcji nie jest unikatowe, kompilator wybierze najbardziej wyspecjalizowaną wersję funkcji szablonu. Ogólna wersja funkcji szablonu

`template`\< **classT**> **void swap**( **t&**, **t&**)

w klasie algorytmu działa przez przypisanie i jest operacją powolnej. Wyspecjalizowana wersja w każdym kontenerze jest znacznie szybsza, ponieważ może pracować z wewnętrzną reprezentacją klasy Container.

### <a name="example"></a>Przykład

Zobacz przykład kodu dla klasy składowej zestaw [wielokrotny:: swap](../standard-library/multiset-class.md#swap)dla przykładu użycia wersji szablonu `swap` .

---
description: Dowiedz się więcej na temat struktury uses_allocator
title: uses_allocator — Struktura
ms.date: 11/04/2016
f1_keywords:
- future/std::uses_allocator
ms.assetid: c418f002-62e9-4806-b70c-41c663cae583
ms.openlocfilehash: 3ece99d12443af2ec28b52e2a0dae72d8af4cc91
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153619"
---
# <a name="uses_allocator-structure"></a>uses_allocator — Struktura

Specjalizacje, które zawsze mają wartość true.

## <a name="syntax"></a>Składnia

```cpp
template <class Ty, class Alloc>
struct uses_allocator<promise<Ty>, Alloc> : true_type;
template <class Ty, class Alloc>
struct uses_allocator<packaged_task<Ty>, Alloc> : true_type;
```

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<future>

**Przestrzeń nazw:** std

## <a name="specializations"></a>Specjalizacje

### <a name="tuple"></a><a name="tuple"></a> \<tuple>

```cpp
template <class... Types, class Alloc>
struct uses_allocator<tuple<Types...>, Alloc>;
```

## <a name="see-also"></a>Zobacz też

[Dokumentacja plików nagłówkowych](../standard-library/cpp-standard-library-header-files.md)\
[\<future>](../standard-library/future.md)

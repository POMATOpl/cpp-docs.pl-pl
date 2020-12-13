---
description: Dowiedz się więcej na temat struktury piecewise_contruct_t
title: Struktura piecewise_contruct_t
ms.date: 11/04/2016
f1_keywords:
- utility/std::piecewise_contruct_t
helpviewer_keywords:
- piecewise_contruct_t class
- piecewise_contruct_t structure
ms.openlocfilehash: 7fefacff75b47c25cb9ae07cc894498eadb551df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340752"
---
# <a name="piecewise_contruct_t-structure"></a>Struktura piecewise_contruct_t

Struktura `piecewise_construct_t` jest pustym typem struktury używanym do zachowywania osobnego konstruktora i przeciążania funkcji. W `pair` odniesieniu do programu ma Konstruktor z `piecewise_construct_t` pierwszym argumentem, po którym następuje dwa `tuple` argumenty.

## <a name="syntax"></a>Składnia

```cpp
struct piecewise_construct_t { explicit piecewise_construct_t() = default; };

inline constexpr piecewise_construct_t piecewise_construct{};
```

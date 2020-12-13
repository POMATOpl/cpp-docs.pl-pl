---
description: Dowiedz się więcej na temat struktury nothrow_t
title: nothrow_t — Struktura
ms.date: 11/04/2016
f1_keywords:
- nothrow_t
helpviewer_keywords:
- nothrow_t class
ms.assetid: dc7d5d42-ed5a-4919-88fe-bbad519b7a1d
ms.openlocfilehash: 974fbe3a1e27da41c6366c62d748426293a54437
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338095"
---
# <a name="nothrow_t-structure"></a>nothrow_t — Struktura

Struktura jest używana jako parametr funkcji dla operatora new, aby wskazać, że funkcja powinna zwrócić wskaźnik o wartości null, aby zgłosić błąd alokacji, zamiast zgłosić wyjątek.

## <a name="syntax"></a>Składnia

```cpp
struct std::nothrow_t {};
```

## <a name="remarks"></a>Uwagi

Struktura pomaga kompilatorowi wybrać poprawną wersję konstruktora. [nothrow](../standard-library/new-functions.md#nothrow) jest synonimem dla obiektów typu `std::nothrow_t` .

## <a name="example"></a>Przykład

Zobacz [operator new](../standard-library/new-operators.md#op_new) i [operator new&#91;&#93;](../standard-library/new-operators.md#op_new_arr) , aby poznać przykłady `std::nothrow_t` użycia jako parametru funkcji.

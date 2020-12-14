---
description: Dowiedz się więcej na temat struktury default_delete
title: Struktura default_delete
ms.date: 04/04/2019
f1_keywords:
- memory/std::default_delete
helpviewer_keywords:
- default_delete struct
ms.openlocfilehash: 5b7d652dbb556957acf96ba63ac9ce14b628fb7e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97232970"
---
# <a name="default_delete-struct"></a>Struktura default_delete

Wstępnie zdefiniowany obiekt funkcji, który wykonuje operację dzielenia ( `operator/` ) dla jej argumentów.

## <a name="syntax"></a>Składnia

```cpp
template <class T>
    struct default_delete
```

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<memory>

**Przestrzeń nazw:** std

## <a name="members"></a>Elementy członkowskie

### <a name="constructors"></a>Konstruktory

|Nazwa|Opis|
|-|-|
|[default_delete](#default_delete)|Konstruktor dla obiektów typu `default_delete` .|

### <a name="operators"></a>Operatory

|Nazwa|Opis|
|-|-|
|[operator ()](#op_paren)|Operator odwołania, do którego można uzyskać dostęp `default_delete` .|

## <a name="default_delete"></a><a name="default_delete"></a> default_delete

Konstruktor dla obiektów typu `default_delete` .

```cpp
constexpr default_delete() noexcept = default;
template <class U>
    default_delete(const default_delete<U>&) noexcept;
```

## <a name="operator"></a><a name="op_paren"></a> operator ()

Operator odwołania, do którego można uzyskać dostęp `default_delete` .

```cpp
void operator()(T*) const;
```

## <a name="see-also"></a>Zobacz też

[\<memory>](../standard-library/memory.md)

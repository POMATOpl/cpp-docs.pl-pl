---
title: remove_cv — klasa | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::remove_cv
dev_langs:
- C++
helpviewer_keywords:
- remove_cv class
- remove_cv
ms.assetid: 8502602a-1c80-479c-84e0-33bd1d6496d6
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 80b07d1a07bf0e51e888a96d5cf076375e78106c
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2018
---
# <a name="removecv-class"></a>remove_cv — Klasa

Tworzy typ inny niż const/volatile z typu.

## <a name="syntax"></a>Składnia

```cpp
template <class T>
struct remove_cv;

template <class T>
using remove_cv_t = typename remove_cv<T>::type;
```

### <a name="parameters"></a>Parametry

`T` Typ do zmodyfikowania.

## <a name="remarks"></a>Uwagi

Wystąpienie `remove_cv<T>` przechowuje zmodyfikowane — typ danych `T1` podczas `T` ma postać `const T1`, `volatile T1`, lub `const volatile T1`, w przeciwnym razie `T`.

## <a name="example"></a>Przykład

```cpp
#include <type_traits>
#include <iostream>

int main()
    {
    int *p = (std::remove_cv_t<const volatile int> *)0;

    p = p;  // to quiet "unused" warning
    std::cout << "remove_cv_t<const volatile int> == "
        << typeid(*p).name() << std::endl;

    return (0);
    }
```

```Output
remove_cv_t<const volatile int> == int
```

## <a name="requirements"></a>Wymagania

**Nagłówek:** \<type_traits >

**Namespace:** Standard

## <a name="see-also"></a>Zobacz także

[<type_traits>](../standard-library/type-traits.md)<br/>
[remove_const, klasa](../standard-library/remove-const-class.md)<br/>
[remove_volatile, klasa](../standard-library/remove-volatile-class.md)<br/>

---
description: 'Dowiedz się więcej o: specyfikator Storage-Class statycznej'
title: Specyfikator statycznej klasy magazynowania
ms.date: 11/04/2016
helpviewer_keywords:
- static variables, specifier
- storage classes, static
- static storage class specifiers
ms.assetid: 9bce361e-919b-46b9-8148-40d7ab0eb024
ms.openlocfilehash: da7ca4ea71b3e450da986ec175adcaf08852d81b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97168751"
---
# <a name="static-storage-class-specifier"></a>Specyfikator statycznej klasy magazynowania

Zmienna zadeklarowana na poziomie wewnętrznym ze **`static`** specyfikatorem klasy magazynu ma globalny okres istnienia, ale jest widoczna tylko w bloku, w którym jest zadeklarowana. W przypadku ciągów stałych użycie **`static`** jest przydatne, ponieważ zmniejsza obciążenie częstej inicjalizacji w często wywoływanych funkcjach.

## <a name="remarks"></a>Uwagi

Jeśli zmienna nie zostanie jawnie zainicjowana **`static`** , domyślnie zostanie ona zainicjowana przez 0. Wewnątrz funkcji program **`static`** powoduje przydzielenie magazynu i służy jako definicja. Wewnętrzne zmienne statyczne zapewniają prywatny, stały magazyn widoczny tylko dla jednej funkcji.

## <a name="see-also"></a>Zobacz też

[Klasy magazynu w języku C](c-storage-classes.md)<br/>
[Klasy magazynu (C++)](../cpp/storage-classes-cpp.md)

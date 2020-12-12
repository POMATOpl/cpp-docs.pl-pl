---
description: 'Dowiedz się więcej o: Przydziel'
title: allocate
ms.date: 11/04/2016
f1_keywords:
- allocate_cpp
helpviewer_keywords:
- __declspec keyword [C++], allocate
- allocate __declspec keyword
ms.assetid: 67828b31-de60-4c0e-b0a6-ef3aab22641d
ms.openlocfilehash: 0a30b113ca9271dc53777073ea0a80bac0f16bcb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97288285"
---
# <a name="allocate"></a>allocate

**Specyficzne dla firmy Microsoft**

**`allocate`** Specyfikator deklaracji nazywa segment danych, w którym zostanie przydzielony element danych.

## <a name="syntax"></a>Składnia

> **`__declspec(allocate("`***segname* **`))`** *deklarator*

## <a name="remarks"></a>Uwagi

Nazwa *segname* musi być zadeklarowana przy użyciu jednej z następujących pragm:

- [code_seg](../preprocessor/code-seg.md)

- [const_seg](../preprocessor/const-seg.md)

- [data_seg](../preprocessor/data-seg.md)

- [init_seg](../preprocessor/init-seg.md)

- [Paragraf](../preprocessor/section.md)

## <a name="example"></a>Przykład

```cpp
// allocate.cpp
#pragma section("mycode", read)
__declspec(allocate("mycode"))  int i = 0;

int main() {
}
```

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[`__declspec`](../cpp/declspec.md)<br/>
[Słowa kluczowe](../cpp/keywords-cpp.md)

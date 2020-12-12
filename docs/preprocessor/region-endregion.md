---
description: 'Dowiedz się więcej na temat: region, endregion pragma'
title: region, endregion, pragmy
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.endregion
- endregion_CPP
- region_CPP
- vc-pragma.region
helpviewer_keywords:
- pragmas, region
- pragmas, endregion
- endregion pragma
- region pragma
ms.assetid: c697f807-622f-4796-851b-68a42bbecd84
ms.openlocfilehash: a12305240f0c05913d16c5f26fb64661fc08e736
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167425"
---
# <a name="region-endregion-pragmas"></a>region, endregion, pragmy

`#pragma region` umożliwia określenie bloku kodu, który można rozwijać lub zwijać podczas korzystania z funkcji tworzenia [konspektu](/visualstudio/ide/outlining) edytora Visual Studio Code.

## <a name="syntax"></a>Składnia

> *Nazwa* **regionu #pragma**\
> **#pragma** *komentarz* endregion

### <a name="parameters"></a>Parametry

*komentować*\
Obowiązkowe Komentarz, który ma być wyświetlany w edytorze kodu.

*Nazwij*\
Obowiązkowe Nazwa regionu. Ta nazwa jest wyświetlana w edytorze kodu.

## <a name="remarks"></a>Uwagi

`#pragma endregion` oznacza koniec `#pragma region` bloku.

`#region`Blok musi być zakończony przez `#pragma endregion` dyrektywę.

## <a name="example"></a>Przykład

```cpp
// pragma_directives_region.cpp
#pragma region Region_1
void Test() {}
void Test2() {}
void Test3() {}
#pragma endregion Region_1

int main() {}
```

## <a name="see-also"></a>Zobacz także

[Dyrektywy pragma i słowo kluczowe __pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)

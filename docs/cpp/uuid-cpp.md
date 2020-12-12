---
description: 'Dowiedz się więcej o: UUID (C++)'
title: uuid (C++)
ms.date: 11/04/2016
f1_keywords:
- uuid_cpp
helpviewer_keywords:
- __declspec keyword [C++], uuid
- uuid __declspec keyword
ms.assetid: 9d004621-09bc-4a8d-871b-648f5d5102d7
ms.openlocfilehash: c841bb1813769ab70e756fe4edb7fd351c1dbc49
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116733"
---
# <a name="uuid-c"></a>uuid (C++)

**Specyficzne dla firmy Microsoft**

Kompilator dołącza identyfikator GUID do klasy lub struktury zadeklarowanej lub zdefiniowanej (tylko pełne definicje obiektów COM) z **`uuid`** atrybutem.

## <a name="syntax"></a>Składnia

```
__declspec( uuid("ComObjectGUID") ) declarator
```

## <a name="remarks"></a>Uwagi

**`uuid`** Atrybut przyjmuje ciąg jako argument. Ten ciąg Określa identyfikator GUID w normalnym formacie rejestru z ogranicznikami **{}** lub bez nich. Na przykład:

```cpp
struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) IUnknown;
struct __declspec(uuid("{00020400-0000-0000-c000-000000000046}")) IDispatch;
```

Ten atrybut może być stosowany w ponownej deklaracji. Dzięki temu nagłówki systemowe mogą podawać definicje interfejsów, takich jak `IUnknown` , oraz ponowną deklarację w innym nagłówku (na przykład \<comdef.h> ) w celu dostarczenia identyfikatora GUID.

Za pomocą słowa kluczowego [__uuidof](../cpp/uuidof-operator.md) można zastosować do pobrania stałego identyfikatora GUID dołączonego do typu zdefiniowanego przez użytkownika.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[__declspec](../cpp/declspec.md)<br/>
[Słowa kluczowe](../cpp/keywords-cpp.md)

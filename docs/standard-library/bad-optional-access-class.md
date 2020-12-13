---
description: Dowiedz się więcej na temat klasy bad_optional_access
title: Klasa bad_optional_access
ms.date: 08/06/2019
f1_keywords:
- optional/std::bad_optional_access
ms.openlocfilehash: e3439c53766a1890592bde8ed449f5ff2779f347
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97132759"
---
# <a name="bad_optional_access-class"></a>Klasa bad_optional_access

Definiuje typ obiektów zgłoszonych jako wyjątki, aby zgłosić sytuację, w której podjęto próbę uzyskania dostępu do wartości `optional` obiektu, który nie zawiera wartości.

## <a name="syntax"></a>Składnia

```cpp
class bad_optional_access : public exception
{
public:
    bad_optional_access() noexcept;
    bad_optional_access(const bad_optional_access&) noexcept;
    bad_optional_access& operator=(const bad_optional_access&) noexcept;
    const char* what() const noexcept override;
};
```

## <a name="see-also"></a>Zobacz też

[\<optional>](optional.md)\
[optional, klasa](optional-class.md)

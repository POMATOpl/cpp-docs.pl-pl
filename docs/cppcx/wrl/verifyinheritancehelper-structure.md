---
description: Dowiedz się więcej o strukturze VerifyInheritanceHelper
title: VerifyInheritanceHelper — Struktura
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::VerifyInheritanceHelper
- implements/Microsoft::WRL::Details::VerifyInheritanceHelper::Verify
helpviewer_keywords:
- Microsoft::WRL::Details::VerifyInheritanceHelper structure
- Microsoft::WRL::Details::VerifyInheritanceHelper::Verify method
ms.assetid: 8a48a702-0f71-4807-935b-8311f0a7a8b6
ms.openlocfilehash: 672455482a2d21cb695124cad31740b6325c377d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135047"
---
# <a name="verifyinheritancehelper-structure"></a>VerifyInheritanceHelper — Struktura

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

## <a name="syntax"></a>Składnia

```cpp
template <typename I, typename Base>
struct VerifyInheritanceHelper;

template <typename I>
struct VerifyInheritanceHelper<I, Nil>;
```

### <a name="parameters"></a>Parametry

*Mam*<br/>
Typ.

*Opiera*<br/>
Inny typ.

## <a name="remarks"></a>Uwagi

Testuje, czy jeden interfejs pochodzi od innego interfejsu.

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

Nazwa                                       | Opis
------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------
[VerifyInheritanceHelper:: Verify](#verify) | Testuje dwa interfejsy określone przez bieżące parametry szablonu i określa, czy jeden interfejs pochodzi od drugiego.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`VerifyInheritanceHelper`

## <a name="requirements"></a>Wymagania

**Nagłówek:** implementuje. h

**Przestrzeń nazw:** Microsoft:: WRL::D etails

## <a name="verifyinheritancehelperverify"></a><a name="verify"></a> VerifyInheritanceHelper:: Verify

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

```cpp
static void Verify();
```

### <a name="remarks"></a>Uwagi

Testuje dwa interfejsy określone przez bieżące parametry szablonu i określa, czy jeden interfejs pochodzi od drugiego.

Błąd jest emitowany, jeśli jeden interfejs nie pochodzi od drugiego.

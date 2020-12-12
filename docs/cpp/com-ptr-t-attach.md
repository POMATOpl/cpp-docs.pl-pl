---
description: 'Dowiedz się więcej na temat: _com_ptr_t:: Attach'
title: _com_ptr_t::Attach
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::Attach
helpviewer_keywords:
- COM interfaces, attach pointer
- Attach method [C++]
ms.assetid: 94c18e0a-06be-4ca7-bdaf-cd54ec0a645e
ms.openlocfilehash: 5b27a4bd6572f2f1429766328c01f377672ee11d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295656"
---
# <a name="_com_ptr_tattach"></a>_com_ptr_t::Attach

**Specyficzne dla firmy Microsoft**

Hermetyzuje pierwotny wskaźnik interfejsu tego typu inteligentnego wskaźnika.

## <a name="syntax"></a>Składnia

```cpp
void Attach( Interface* pInterface ) throw( );
void Attach( Interface* pInterface, bool fAddRef ) throw( );
```

#### <a name="parameters"></a>Parametry

*pInterface*<br/>
Pierwotny wskaźnik interfejsu.

*fAddRef*<br/>
Jeśli jest **`true`** , to `AddRef` jest wywoływana. Jeśli tak **`false`** , `_com_ptr_t` obiekt przejmuje własność wskaźnika interfejsu RAW bez wywoływania `AddRef` .

## <a name="remarks"></a>Uwagi

- **Dołącz (**  *pInterface*  **)** `AddRef` nie jest wywoływana. Własność interfejsu jest przenoszona do tego `_com_ptr_t` obiektu. `Release` jest wywoływana, aby zmniejszyć liczbę odwołań dla poprzednio hermetyzowanego wskaźnika.

- **Attach (**  *pInterface* **,**  *fAddRef*  **)** Jeśli *fAddRef* jest **`true`** , `AddRef` jest wywoływana, aby zwiększyć liczbę odwołań dla wskaźnika hermetyzowanego interfejsu. Jeśli *fAddRef* jest **`false`** , ten `_com_ptr_t` obiekt przejmuje własność wskaźnika interfejsu RAW bez wywoływania `AddRef` . `Release` jest wywoływana, aby zmniejszyć liczbę odwołań dla poprzednio hermetyzowanego wskaźnika.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Klasa _com_ptr_t](../cpp/com-ptr-t-class.md)

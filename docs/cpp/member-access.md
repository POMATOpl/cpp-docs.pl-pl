---
description: 'Dowiedz się więcej o: dostęp do składowej'
title: Dostęp do elementu członkowskiego
ms.date: 11/04/2016
helpviewer_keywords:
- member-selection operators [C++]
- pointers, smart
- member access, overloaded operators
- operator overloading [C++], member access operators
- smart pointers, definition
- smart pointers
ms.assetid: 8c7b2c43-eb92-4d42-9a8e-61aa37d71333
ms.openlocfilehash: c35eb2e7e24da9f8e8988b47ebfd8a59df815cee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97161718"
---
# <a name="member-access"></a>Dostęp do elementu członkowskiego

Dostęp do elementu członkowskiego klasy może być kontrolowany przez przeładowanie operatora dostępu do elementu członkowskiego ( **->** ). Ten operator jest traktowany jako operator jednoargumentowy w tym użyciu, a funkcja przeciążonego operatora musi być funkcją składową klasy. W związku z tym Deklaracja dla takiej funkcji jest:

## <a name="syntax"></a>Składnia

```
class-type *operator->()
```

## <a name="remarks"></a>Uwagi

gdzie *Class-Type* jest nazwą klasy, do której należy ten operator. Funkcja operatora dostępu do elementu członkowskiego musi być niestatyczną funkcją składową.

Ten operator jest używany (często w połączeniu z operatorem odwołującym wskaźnik) do implementowania "inteligentnych wskaźników", które weryfikują wskaźniki przed wymienieniem lub licznikiem użycia.

Element **.** operator dostępu do składowych nie może być przeciążony.

## <a name="see-also"></a>Zobacz też

[Przeciążanie operatora](../cpp/operator-overloading.md)

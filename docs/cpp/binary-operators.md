---
description: 'Dowiedz się więcej o: operatory binarne'
title: Operatory binarne
ms.date: 06/14/2018
helpviewer_keywords:
- member-selection operators [C++]
- operators [C++], binary
- binary operators [C++]
ms.assetid: c0e7fbff-bc87-4708-8333-504ac09ee83e
ms.openlocfilehash: cfb897a3df7cdb3d76f7af82f694e1cf09284cc7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229603"
---
# <a name="binary-operators"></a>Operatory binarne

W poniższej tabeli przedstawiono listę operatorów, które mogą być przeciążone.

## <a name="redefinable-binary-operators"></a>Przedefiniowane operatory binarne

|Operator|Nazwa|
|--------------|----------|
|**,**|Przecinek|
|**!=**|Nierówność|
|**%**|Modulo|
|**%=**|Moduł/przypisanie|
|**&**|Bitowe ORAZ|
|**&&**|Logiczne AND|
|**&=**|Bitowe i/przypisanie|
|**&#42;**|Mnożenie|
|**&#42;=**|Mnożenie/przypisanie|
|**+**|Dodawanie|
|**+=**|Dodawanie/przypisywanie|
|**-**|Odejmowanie|
|**-=**|Odejmowanie/przypisanie|
|**->**|Wybór elementu członkowskiego|
|**->&#42;**|Wybór wskaźnika do elementu członkowskiego|
|**/**|Dział|
|**/=**|Dzielenie/przypisanie|
|**<**|Mniejsze niż|
|**<<**|Przesunięcie w lewo|
|**<<=**|Przesunięcie w lewo/przypisanie|
|**<=**|Mniejsze niż lub równe|
|**=**|Przypisanie|
|**==**|Równość|
|**>**|Większe niż|
|**>=**|Większe niż lub równe|
|**>>**|Przesunięcie w prawo|
|**>>=**|Przesunięcie w prawo/przypisanie|
|**^**|Wyłączny lub|
|**^=**|Wyłączne lub/przypisanie|
|**&#124;**|Bitowe alternatywne OR|
|**&#124;=**|Przypisanie bitowe lub//|
|**&#124;&#124;**|Logiczne OR|

Aby zadeklarować funkcję operatora binarnego jako niestatyczną składową, należy zadeklarować ją w postaci:

> *RET-Type* **`operator`** *op* **(** *ARG* **)**

gdzie *RET-Type* jest typem zwracanym, *op* jest jednym z operatorów wymienionych w powyższej tabeli *, a argument* jest argumentem dowolnego typu.

Aby zadeklarować funkcję operatora binarnego jako funkcję globalną, należy zadeklarować ją w postaci:

> *RET-Type* **`operator`** *op* **(** _arg1_**,** _arg2_ **)**

gdzie *RET-Type* i *op* są zgodnie z opisem dla funkcji operatora składowych, a *arg1* i *arg2* są argumentami. Co najmniej jeden z argumentów musi być typu klasy.

> [!NOTE]
> Nie ma ograniczeń dla zwracanych typów operatorów binarnych; Jednak większość operatorów binarnych zdefiniowanych przez użytkownika zwraca typ klasy lub odwołanie do typu klasy.

## <a name="see-also"></a>Zobacz też

[Przeciążanie operatora](../cpp/operator-overloading.md)

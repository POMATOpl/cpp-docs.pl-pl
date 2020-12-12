---
description: 'Dowiedz się więcej na temat: zmiana nazwy atrybutu importu'
title: Zmień nazwę atrybutu importu
ms.date: 08/29/2019
helpviewer_keywords:
- rename attribute
ms.assetid: 5c5c6153-1087-4b7b-87fb-fc59b90b9975
ms.openlocfilehash: 3003300887dadbab5cf05396ff3fa38b6dd29026
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176603"
---
# <a name="rename-import-attribute"></a>Zmień nazwę atrybutu importu

**Specyficzne dla języka C++**

Działa wokół problemów z kolizją nazw.

## <a name="syntax"></a>Składnia

> **#import** **zmianę nazwy** *biblioteki typów* ("*StaraNazwa*" **,** "*newname*" **)**

### <a name="parameters"></a>Parametry

*StaraNazwa*\
Stara nazwa w bibliotece typów.

*NewName*\
Nazwa, która ma być używana zamiast starej nazwy.

## <a name="remarks"></a>Uwagi

Po określeniu atrybutu **zmiany nazwy** kompilator zastępuje wszystkie wystąpienia elementu *StaraNazwa* w *bibliotece typów* z nazwą *pliku w plikach* nagłówkowych określoną przez użytkownika.

Atrybutu **zmiany nazwy** można użyć, gdy nazwa w bibliotece typów jest zgodna z definicją makra w plikach nagłówkowych systemu. Jeśli ta sytuacja nie zostanie rozwiązana, kompilator może wydać różne błędy składniowe, takie jak [błąd kompilatora C2059](../error-messages/compiler-errors-1/compiler-error-c2059.md) i [błąd kompilatora C2061](../error-messages/compiler-errors-1/compiler-error-c2061.md).

> [!NOTE]
> Zastąpienie dotyczy nazwy użytej w bibliotece typów, a nie nazwy użytej w pliku nagłówkowym.

Załóżmy na przykład, że właściwość o nazwie `MyParent` istnieje w bibliotece typów, a makro `GetMyParent` jest zdefiniowane w pliku nagłówkowym i używane wcześniej `#import` . Ponieważ `GetMyParent` jest to domyślna nazwa funkcji otoki dla właściwości obsługa błędów `get` , zostanie wystąpiła kolizja nazw. Aby obejść ten problem, użyj następującego atrybutu w `#import` instrukcji:

```cpp
#import MyTypeLib.tlb rename("MyParent","MyParentX")
```

który zmienia nazwę `MyParent` w bibliotece typów. Próba zmiany nazwy `GetMyParent` otoki zakończy się niepowodzeniem:

```cpp
#import MyTypeLib.tlb rename("GetMyParent","GetMyParentX")
```

Jest to spowodowane faktem, że nazwa `GetMyParent` występuje tylko w pliku nagłówkowym biblioteki typów.

**ZAKOŃCZENIE specyficzne dla języka C++**

## <a name="see-also"></a>Zobacz też

[Atrybuty #import](../preprocessor/hash-import-attributes-cpp.md)\
[#import — dyrektywa](../preprocessor/hash-import-directive-cpp.md)

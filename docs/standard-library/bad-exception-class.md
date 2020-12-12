---
description: Dowiedz się więcej na temat klasy bad_exception
title: Klasa bad_exception
ms.date: 11/04/2016
f1_keywords:
- exception/std::bad_exception
helpviewer_keywords:
- bad_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
ms.openlocfilehash: 6b47facc751e1f16e033f26be284db1287e79ea8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321615"
---
# <a name="bad_exception-class"></a>Klasa bad_exception

Klasa opisuje wyjątek, który może zostać wygenerowany z nieoczekiwanej procedury obsługi.

## <a name="syntax"></a>Składnia

```cpp
class bad_exception : public exception {};

bad_exception();
bad_exception(const bad_exception&);
bad_exception& operator=(const bad_exception&);
const char* what() const override;
```

## <a name="remarks"></a>Uwagi

[nieoczekiwane](../standard-library/exception-functions.md#unexpected) zgłoszenie zostanie `bad_exception` zamiast kończące lub zamiast wywołać inną funkcję określoną za pomocą [set_unexpected](../standard-library/exception-functions.md#set_unexpected) `bad_exception` , jeśli znajduje się na liście throw funkcji.

Wartość zwrócona przez `what` to ciąg języka C zdefiniowany przez implementację. Żadna z funkcji Członkowskich nie zgłasza żadnych wyjątków.

Aby uzyskać listę elementów członkowskich dziedziczonych przez `bad_exception` klasę, zobacz [Klasa wyjątków](../standard-library/exception-class.md).

## <a name="example"></a>Przykład

Zobacz [set_unexpected](../standard-library/exception-functions.md#set_unexpected) , aby zapoznać się z przykładem użycia [nieoczekiwanego](../standard-library/exception-functions.md#unexpected) wyrzucania `bad_exception` .

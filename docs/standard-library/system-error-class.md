---
description: Dowiedz się więcej na temat klasy system_error
title: system_error — Klasa
ms.date: 11/04/2016
f1_keywords:
- system_error/std::system_error
helpviewer_keywords:
- system_error class
ms.assetid: 2eeaacbb-8a4a-4ad7-943a-997901a77f32
ms.openlocfilehash: 51e629e9fffca6ec82e06521d1d81174da5ff1f3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97183168"
---
# <a name="system_error-class"></a>system_error — Klasa

Reprezentuje klasę bazową dla wszystkich wyjątków zgłoszonych w celu zgłaszania błędu systemu niskiego poziomu.

## <a name="syntax"></a>Składnia

```cpp
class system_error : public runtime_error {
    explicit system_error(error_code _Errcode, const string& _Message = "");
    system_error(error_code _Errcode, const char *_Message);
    system_error(error_code::value_type _Errval, const error_category& _Errcat, const string& _Message);
    system_error(error_code::value_type _Errval, const error_category& _Errcat, const char *_Message);

    const error_code& code() const throw();
    const char* what() const noexcept override;
};
```

## <a name="remarks"></a>Uwagi

Wartość zwrócona przez `what` [wyjątek](../standard-library/exception-class.md) klasy jest tworzona z `_Message` i przechowywany obiekt typu [error_code](../standard-library/error-code-class.md) ( `code` lub `error_code(_Errval, _Errcat)` ).

Funkcja członkowska `code` zwraca przechowywany obiekt [error_code](../standard-library/error-code-class.md) .

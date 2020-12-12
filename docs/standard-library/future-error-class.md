---
description: Dowiedz się więcej na temat klasy future_error
title: future_error — Klasa
ms.date: 11/04/2016
f1_keywords:
- future/std::future_error
ms.assetid: 6071c545-ac2a-49ef-9967-07b0125da861
ms.openlocfilehash: c7dc99ea842cd13658c13a5c2492bda3d853302f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324216"
---
# <a name="future_error-class"></a>future_error — Klasa

Opisuje obiekt wyjątku, który może być zgłaszany przez metody typów, które zarządzają [przyszłymi](../standard-library/future-class.md) obiektami.

## <a name="syntax"></a>Składnia

```cpp
class future_error : public logic_error {
public:
    future_error(error_code code);

const error_code& code() const throw();

const char *what() const throw();

};
```

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<future>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[Dokumentacja plików nagłówkowych](../standard-library/cpp-standard-library-header-files.md)\
[Klasa logic_error](../standard-library/logic-error-class.md)\
[Klasa error_code](../standard-library/error-code-class.md)

---
description: Dowiedz się więcej o klasie wyjątków
title: Klasa exception
ms.date: 11/04/2016
f1_keywords:
- exception/std::exception
helpviewer_keywords:
- exception class
ms.assetid: 4f181f67-5888-4b50-89a6-745091ffb2fe
ms.openlocfilehash: a2061a2609017872145b12b4863e939788a123cf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324452"
---
# <a name="exception-class"></a>Klasa exception

Klasa służy jako klasa bazowa dla wszystkich wyjątków zgłoszonych przez niektóre wyrażenia i przez standardową bibliotekę języka C++.

## <a name="syntax"></a>Składnia

```cpp
class exception {
   public:
   exception();
   exception(const char* const &message);
   exception(const char* const &message, int);
   exception(const exception &right);
   exception& operator=(const exception &right);
   virtual ~exception();
   virtual const char *what() const;
};
```

## <a name="remarks"></a>Uwagi

W przypadku tej klasy podstawowej jest to katalog główny klas wyjątków standardowych zdefiniowanych w [\<stdexcept>](../standard-library/stdexcept.md) . Wartość ciągu języka C zwrócona przez `what` jest pozostawiana nieokreślona przez Konstruktor domyślny, ale może być zdefiniowana przez konstruktory dla niektórych klas pochodnych jako ciąg języka C zdefiniowany przez implementację. Żadna z funkcji Członkowskich nie zgłasza żadnych wyjątków.

**`int`** Parametr pozwala określić, że żadna pamięć nie powinna być przypisana. Wartość elementu **`int`** jest ignorowana.

> [!NOTE]
> Konstruktory `exception(const char* const &message)` i `exception(const char* const &message, int)` są rozszerzeniami firmy Microsoft do standardowej biblioteki języka C++.

## <a name="example"></a>Przykład

Aby zapoznać się z przykładami użycia klas wyjątków standardowych, które dziedziczą z `exception` klasy, zobacz dowolną z klas zdefiniowanych w [\<stdexcept>](../standard-library/stdexcept.md) .

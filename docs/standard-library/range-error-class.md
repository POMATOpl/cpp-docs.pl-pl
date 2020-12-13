---
description: Dowiedz się więcej na temat klasy range_error
title: range_error — Klasa
ms.date: 08/14/2018
f1_keywords:
- stdexcept/std::range_error
helpviewer_keywords:
- range_error class
ms.assetid: 8afb3e88-fc49-4213-b096-ed63d7aea37c
ms.openlocfilehash: c9d1ef328ba077b4b675d782df9c85d2db3a2072
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337955"
---
# <a name="range_error-class"></a>range_error — Klasa

Klasa służy jako klasa bazowa dla wszystkich wyjątków zgłoszonych w celu zgłaszania błędu zakresu.

## <a name="syntax"></a>Składnia

```cpp
class range_error : public runtime_error {
public:
    explicit range_error(const string& message);
    explicit range_error(const char *message);
};
```

## <a name="remarks"></a>Uwagi

Wartość zwrócona przez [co](../standard-library/exception-class.md) to jest kopia `message.data` . Aby uzyskać więcej informacji, zobacz [basic_string::d ATA](../standard-library/basic-string-class.md#data).

## <a name="example"></a>Przykład

```cpp
// range_error.cpp
// compile with: /EHsc /GR
#include <iostream>
using namespace std;
int main()
{
   try
   {
      throw range_error( "The range is in error!" );
   }
   catch (range_error &e)
   {
      cerr << "Caught: " << e.what( ) << endl;
      cerr << "Type: " << typeid( e ).name( ) << endl;
   };
}
/* Output:
Caught: The range is in error!
Type: class std::range_error
*/
```

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<stdexcept>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[Klasa runtime_error](../standard-library/runtime-error-class.md)\
[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

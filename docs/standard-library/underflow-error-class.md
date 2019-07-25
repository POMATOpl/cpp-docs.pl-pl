---
title: underflow_error — Klasa
ms.date: 11/04/2016
f1_keywords:
- stdexcept/std::underflow_error
helpviewer_keywords:
- underflow_error class
ms.assetid: d632f1f9-9c6c-4954-b96b-03041bfab22d
ms.openlocfilehash: 41e3c8606cb8c6c90a84927f01eb953be138534a
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454990"
---
# <a name="underflowerror-class"></a>underflow_error — Klasa

Klasa służy jako klasa bazowa dla wszystkich wyjątków zgłoszonych do zgłaszania niedopełnienia arytmetycznego.

## <a name="syntax"></a>Składnia

```cpp
class underflow_error : public runtime_error {
public:
    explicit underflow_error(const string& message);

    explicit underflow_error(const char *message);

};
```

## <a name="remarks"></a>Uwagi

Wartość zwracana przez [co](../standard-library/exception-class.md) to jest kopia[danych](../standard-library/basic-string-class.md#data) **komunikatów**`.`.

## <a name="example"></a>Przykład

```cpp
// underflow_error.cpp
// compile with: /EHsc /GR
#include <iostream>

using namespace std;

int main( )
{
   try
   {
      throw underflow_error( "The number's a bit small, captain!" );
   }
   catch ( exception &e ) {
      cerr << "Caught: " << e.what( ) << endl;
      cerr << "Type: " << typeid( e ).name( ) << endl;
   };
}
/* Output:
Caught: The number's a bit small, captain!
Type: class std::underflow_error
*/
```

## <a name="requirements"></a>Wymagania

**Nagłówek:** \<stdexcept >

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz także

[Klasa runtime_error](../standard-library/runtime-error-class.md)\
[Bezpieczeństwo wątku w standardowej bibliotece C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

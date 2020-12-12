---
description: Dowiedz się więcej na temat klasy underflow_error
title: underflow_error — Klasa
ms.date: 11/04/2016
f1_keywords:
- stdexcept/std::underflow_error
helpviewer_keywords:
- underflow_error class
ms.assetid: d632f1f9-9c6c-4954-b96b-03041bfab22d
ms.openlocfilehash: 638f824ab5c74a57f7130ea4fdbb3aae3da27e18
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97132733"
---
# <a name="underflow_error-class"></a>underflow_error — Klasa

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

Wartość zwracana przez `what()` to jest kopia `message.data()` . Aby uzyskać więcej informacji, zobacz [`what`](../standard-library/exception-class.md) i [`data`](../standard-library/basic-string-class.md#data) .

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

**Nagłówek:**\<stdexcept>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[Klasa runtime_error](../standard-library/runtime-error-class.md)\
[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

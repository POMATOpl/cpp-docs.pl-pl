---
description: Dowiedz się więcej na temat klasy runtime_error
title: runtime_error — Klasa
ms.date: 11/04/2016
f1_keywords:
- stdexcept/std::runtime_error
helpviewer_keywords:
- runtime_error class
ms.assetid: 4d0227bf-847b-45a2-a320-2351ebf98368
ms.openlocfilehash: 6fd4bb843502d72e61afc5617d6a9c160f5cc434
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148905"
---
# <a name="runtime_error-class"></a>runtime_error — Klasa

Klasa służy jako klasa bazowa dla wszystkich wyjątków zgłoszonych w celu zgłaszania błędów, które mogą być wykrywalne tylko wtedy, gdy program jest wykonywany.

## <a name="syntax"></a>Składnia

```cpp
class runtime_error : public exception {
public:
    explicit runtime_error(const string& message);

    explicit runtime_error(const char *message);

};
```

## <a name="remarks"></a>Uwagi

Wartość zwracana przez `what()` to jest kopia `message.data()` . Aby uzyskać więcej informacji, zobacz [`what`](../standard-library/exception-class.md) i [`data`](../standard-library/basic-string-class.md#data) .

## <a name="example"></a>Przykład

```cpp
// runtime_error.cpp
// compile with: /EHsc /GR
#include <iostream>

using namespace std;

int main( )
{
// runtime_error
   try
   {
      locale loc( "test" );
   }
   catch ( exception &e )
   {
      cerr << "Caught " << e.what( ) << endl;
      cerr << "Type " << typeid( e ).name( ) << endl;
   };
}
/* Output:
Caught bad locale name
Type class std::runtime_error
*/
```

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<stdexcept>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[Klasa wyjątku](../standard-library/exception-class.md)\
[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

---
title: underflow_error — klasa | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- stdexcept/std::underflow_error
dev_langs:
- C++
helpviewer_keywords:
- underflow_error class
ms.assetid: d632f1f9-9c6c-4954-b96b-03041bfab22d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a1886a1da667ed038e677c6dd3395058ecd13078
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/08/2018
---
# <a name="underflowerror-class"></a>underflow_error — Klasa

Klasa służy jako klasa podstawowa dla wszystkich wyjątków zgłaszanych do zgłaszania arytmetycznego underflow.

## <a name="syntax"></a>Składnia

```cpp
class underflow_error : public runtime_error {
public:
    explicit underflow_error(const string& message);

    explicit underflow_error(const char *message);

};
```

## <a name="remarks"></a>Uwagi

Wartość zwrócona przez [co](../standard-library/exception-class.md) kopię **komunikat**`.`[danych](../standard-library/basic-string-class.md#data).

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
\* Output:
Caught: The number's a bit small, captain!
Type: class std::underflow_error
*\
```

## <a name="requirements"></a>Wymagania

**Nagłówek:** \<stdexcept — >

**Namespace:** Standard

## <a name="see-also"></a>Zobacz także

[\<stdexcept — > elementy członkowskie](http://msdn.microsoft.com/en-us/7b6b0a73-916e-44aa-9a3f-f5b6b3ce98e6)<br/>
[runtime_error, klasa](../standard-library/runtime-error-class.md)<br/>
[Bezpieczeństwo wątku w standardowej bibliotece C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>

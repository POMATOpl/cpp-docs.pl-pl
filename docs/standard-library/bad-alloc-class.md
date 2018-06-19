---
title: bad_alloc — klasa | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- new/std::bad_alloc
dev_langs:
- C++
helpviewer_keywords:
- bad_alloc class
ms.assetid: 6429a8e6-5a49-4907-8d56-f4a4ec8131d0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9ab496a5de8062f6888b92b318788ff72345bc7c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2018
ms.locfileid: "33850733"
---
# <a name="badalloc-class"></a>bad_alloc — Klasa

Klasa opisuje wyjątek, aby wskazać, że żądanie alokacji nie powiodła się.

## <a name="syntax"></a>Składnia

```cpp
class bad_alloc : public exception {
    bad_alloc();
virtual ~bad_alloc();

};
```

## <a name="remarks"></a>Uwagi

Wartość zwrócona przez **co** to ciąg C zdefiniowane w implementacji. Brak funkcji Członkowskich generują żadnych wyjątków.

## <a name="requirements"></a>Wymagania

**Nagłówek:** \<nowy >

**Namespace:** Standard

## <a name="example"></a>Przykład

```cpp
// bad_alloc.cpp
// compile with: /EHsc
#include<new>
#include<iostream>
using namespace std;

int main() {
   char* ptr;
   try {
      ptr = new char[(~unsigned int((int)0)/2) - 1];
      delete[] ptr;
   }
   catch( bad_alloc &ba) {
      cout << ba.what( ) << endl;
   }
}
```

## <a name="sample-output"></a>Przykładowe dane wyjściowe

```Output
bad allocation
```

## <a name="requirements"></a>Wymagania

**Nagłówek:** \<nowy >

## <a name="see-also"></a>Zobacz też

[wyjątek klasy](../standard-library/exception-class.md) [bezpieczeństwo wątku w standardowej bibliotece C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

---
title: 'Jeden&#39;s Operator dopełnienia jednostkowego: ~ | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- "~"
dev_langs:
- C++
helpviewer_keywords:
- tilde (~) one's complement operator
- one's complement operator
- bitwise-complement operator
- compl operator
- ~ operator [C++], syntax
ms.assetid: 4bf81967-34f7-4b4b-aade-fd03d5da0174
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a10c8f3df2a1f2f27ee33450a52132e8184d4232
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2018
---
# <a name="one39s-complement-operator-"></a>Jeden&#39;s Operator dopełnienia jednostkowego: ~
## <a name="syntax"></a>Składnia  
  
```  
  
~ cast-expression  
```  
  
## <a name="remarks"></a>Uwagi  
 Operator dopełnienia jednostkowego swoich (`~`), czasami nazywane operator "dopełnienia bitowego", daje bitowej, jeden dla dopełnienia jej argument. Każdy bit, który jest 1 argument operacji jest 0, w wyniku. Z drugiej strony każdy bit, który ma wartość 0 argument wynosi 1, w wyniku. Argument operacji do swoich operatorem dopełnienia musi być typem całkowitym.  
  
## <a name="operator-keyword-for-"></a>Operator — słowo kluczowe dla ~  
 `compl` Operator jest odpowiednikiem tekstu `~`. Istnieją dwa sposoby `compl` operatora w programach: uwzględnić plik nagłówka `iso646.h`, lub skompiluj z [/Za](../build/reference/za-ze-disable-language-extensions.md).  
  
## <a name="example"></a>Przykład  
  
```  
// expre_One_Complement_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
  
int main () {  
   unsigned short y = 0xFFFF;  
   cout << hex << y << endl;  
   y = ~y;   // Take one's complement  
   cout << hex << y << endl;  
}  
```  
  
 W tym przykładzie, nowa wartość jest przypisywana do `y` jest uzupełnieniem, w wartości bez znaku 0xFFFF lub 0x0000.  
  
 Promocję typu całkowitego odbywa się na całkowite argumentów operacji, a wynikowy typ jest typem, do którego zostanie podniesiona argument. Zobacz [konwersje standardowe](standard-conversions.md) uzyskać więcej informacji na temat jak jest wykonywane podwyższenia poziomu.  
  
## <a name="see-also"></a>Zobacz też  
 [Wyrażenia z operatorami Jednoargumentowymi](../cpp/expressions-with-unary-operators.md)   
 [Operatory C++ wbudowanych, priorytet i łączność](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Jednoargumentowe operatory arytmetyczne](../c-language/unary-arithmetic-operators.md)
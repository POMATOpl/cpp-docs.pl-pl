---
description: 'Dowiedz się więcej o: manipulowania strumieni wyjściowych z jednym argumentem (int lub Long)'
title: Manipulatory strumieni wyjściowych z jednym argumentem (int lub long)
ms.date: 11/04/2016
helpviewer_keywords:
- output streams, int or long argument manipulators
ms.assetid: 338f3164-b5e2-4c5a-a605-7d9dc3629ca1
ms.openlocfilehash: e04486f7d207731d9fbf7ba8083ffcb02a82ba8a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340895"
---
# <a name="output-stream-manipulators-with-one-argument-int-or-long"></a>Manipulatory strumieni wyjściowych z jednym argumentem (int lub long)

Biblioteka klas iostream zawiera zestaw makr do tworzenia sparametryzowanych manipulowania. Manipulowanie za pomocą jednego **`int`** lub **`long`** argumentu jest szczególnym przypadkiem. Aby utworzyć Manipulator strumienia wyjściowego, który akceptuje pojedynczy **`int`** lub **`long`** argument (na przykład `setw` ), należy użyć makra _Smanip, który jest zdefiniowany w \<iomanip> . Ten przykład definiuje `fillblank` manipulator, który wstawia określoną liczbę pustych znaków do strumienia:

## <a name="example"></a>Przykład

```cpp
// output_stream_manip.cpp
// compile with: /GR /EHsc
#include <iostream>
#include <iomanip>
using namespace std;

void fb( ios_base& os, int l )
{
   ostream *pos = dynamic_cast<ostream*>(&os);
   if (pos)
   {
      for( int i=0; i < l; i++ )
      (*pos) << ' ';
   };
}

_Smanip<int>
   __cdecl fillblank(int no)
   {
   return (_Smanip<int>(&fb, no));
   }

int main( )
{
   cout << "10 blanks follow" << fillblank( 10 ) << ".\n";
}
```

## <a name="see-also"></a>Zobacz także

[Niestandardowe manipulowanie z argumentami](../standard-library/custom-manipulators-with-arguments.md)

---
description: 'Dowiedz się więcej na temat: binarne pliki wyjściowe'
title: Binarne pliki wyjściowe
ms.date: 11/04/2016
helpviewer_keywords:
- I/O [C++], binary output files
- files [C++], binary output files
- binary data, binary output files
ms.assetid: 180954af-8cd6-444b-9a76-2f630a3389d8
ms.openlocfilehash: acbefe8eb7f091bf3d323f25ff00464068d9b1f3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325521"
---
# <a name="binary-output-files"></a>Binarne pliki wyjściowe

Strumienie zostały pierwotnie zaprojektowane dla tekstu, więc domyślny tryb wyjściowy to Text. W trybie tekstowym znak wysuwu wiersza (nowy wiersz) jest rozszerzany do pary wysuwu wiersza powrotu karetki. Rozszerzanie może spowodować problemy, jak pokazano poniżej:

```cpp
// binary_output_files.cpp
// compile with: /EHsc
#include <fstream>
using namespace std;
int iarray[2] = { 99, 10 };
int main( )
{
    ofstream os( "test.dat" );
    os.write( (char *) iarray, sizeof( iarray ) );
}
```

Może się spodziewać, że ten program będzie wyprowadzać sekwencję bajtów {99, 0, 10, 0}; Zamiast tego zwraca {99, 0, 13, 10, 0}, co powoduje problemy dla programu oczekiwanie na dane wejściowe binarne. Jeśli potrzebujesz prawdziwe dane wyjściowe binarne, w których znaki są zapisywane nieprzetłumaczone, możesz określić binarne dane wyjściowe przy użyciu argumentu [](../standard-library/basic-ofstream-class.md#basic_ofstream) konstruktora ofstream `openmode` :

```cpp
// binary_output_files2.cpp
// compile with: /EHsc
#include <fstream>
using namespace std;
int iarray[2] = { 99, 10 };

int main()
{
   ofstream ofs ( "test.dat", ios_base::binary );

   // Exactly 8 bytes written
   ofs.write( (char*)&iarray[0], sizeof(int)*2 );
}
```

## <a name="see-also"></a>Zobacz też

[Strumienie wyjściowe](../standard-library/output-streams.md)

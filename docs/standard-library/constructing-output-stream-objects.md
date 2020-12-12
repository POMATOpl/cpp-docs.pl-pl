---
description: 'Dowiedz się więcej o: Konstruowanie obiektów strumienia wyjściowego'
title: Konstruowanie obiektów strumienia wyjściowego
ms.date: 11/04/2016
helpviewer_keywords:
- output stream objects
ms.assetid: 93c8eab6-610c-4f48-b76d-1d960cac7641
ms.openlocfilehash: e730e4cb675b216fa56b5624feb69fadcd61400a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97233646"
---
# <a name="constructing-output-stream-objects"></a>Konstruowanie obiektów strumienia wyjściowego

Jeśli używasz tylko wstępnie zdefiniowanych `cout` , `cerr` lub `clog` obiektów, nie musisz tworzyć strumienia wyjściowego. Należy użyć konstruktorów dla:

- [Konstruktory strumienia plików wyjściowych](#vclrfoutputfilestreamconstructorsanchor1)

- [Konstruktory strumienia ciągów wyjściowych](#vclrfoutputstringstreamconstructorsanchor2)

## <a name="output-file-stream-constructors"></a><a name="vclrfoutputfilestreamconstructorsanchor1"></a> Konstruktory strumienia plików wyjściowych

Strumień pliku wyjściowego można skonstruować na jeden z dwóch sposobów:

- Użyj konstruktora domyślnego, a następnie Wywołaj `open` funkcję członkowską.

   ```cpp
   ofstream myFile; // Static or on the stack
   myFile.open("filename");

   ofstream* pmyFile = new ofstream; // On the heap
   pmyFile->open("filename");
   ```

- Określ nazwę pliku i flagi trybu w wywołaniu konstruktora.

   ```cpp
   ofstream myFile("filename", ios_base::out);
   ```

## <a name="output-string-stream-constructors"></a><a name="vclrfoutputstringstreamconstructorsanchor2"></a> Konstruktory strumienia ciągów wyjściowych

Aby utworzyć strumień ciągu wyjściowego, można użyć `ostringstream` w następujący sposób:

```cpp
using namespace std;
// ...
ostringstream myString;
myString << "this is a test" << ends;

string sp = myString.str(); // Obtain string
cout << sp << endl;
```

`ends`"Manipulator" dodaje do ciągu niezbędny kończący znak null.

## <a name="see-also"></a>Zobacz też

[Strumienie wyjściowe](../standard-library/output-streams.md)

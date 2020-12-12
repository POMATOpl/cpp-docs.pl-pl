---
description: Dowiedz się więcej na temat tworzenia obiektów strumienia wejściowego
title: Konstruowanie obiektów strumienia danych wejściowych
ms.date: 11/04/2016
helpviewer_keywords:
- input stream objects
ms.assetid: ab94866e-6ffe-4f15-b4db-0bd23e636075
ms.openlocfilehash: 2ee1e0bb310c608b53a79afd101aaeafb3cb6645
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324922"
---
# <a name="constructing-input-stream-objects"></a>Konstruowanie obiektów strumienia danych wejściowych

Jeśli używasz tylko `cin` obiektu, nie musisz tworzyć strumienia wejściowego. Należy skonstruować strumień wejściowy, jeśli używasz:

- [Konstruktory strumienia plików wejściowych](#vclrfinputfilestreamconstructorsanchor8)

- [Konstruktory strumienia ciągów wejściowych](#vclrfinputstringstreamconstructorsanchor9)

## <a name="input-file-stream-constructors"></a><a name="vclrfinputfilestreamconstructorsanchor8"></a> Konstruktory strumienia plików wejściowych

Istnieją dwa sposoby tworzenia strumienia pliku wejściowego:

- Użyj **`void`** konstruktora argumentów, a następnie Wywołaj `open` funkcję członkowską:

   ```cpp
   ifstream myFile; // On the stack
   myFile.open("filename");

   ifstream* pmyFile = new ifstream; // On the heap
   pmyFile->open("filename");
   ```

- Określ nazwę pliku i flagi trybu w wywołaniu konstruktora, co spowoduje otwarcie pliku podczas procesu konstrukcji:

   ```cpp
   ifstream myFile("filename");
   ```

## <a name="input-string-stream-constructors"></a><a name="vclrfinputstringstreamconstructorsanchor9"></a> Konstruktory strumienia ciągów wejściowych

Konstruktory strumienia ciągów wejściowych wymagają adresu wstępnie przydzieloną, wstępnie zainicjowany magazyn:

```cpp
string s("123.45");

double amt;
istringstream myString(s);

//istringstream myString("123.45") also works
myString>> amt; // amt contains 123.45
```

## <a name="see-also"></a>Zobacz też

[Strumienie wejściowe](../standard-library/input-streams.md)

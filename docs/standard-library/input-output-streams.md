---
description: 'Dowiedz się więcej o: strumienie danych wejściowych/wyjściowych'
title: Strumienie Input-Output
ms.date: 11/04/2016
helpviewer_keywords:
- I/O [C++], stream
- stream I/O
ms.assetid: 21a97566-91a7-42d6-b2f8-a4c16bc926f1
ms.openlocfilehash: fd261bfdac5b9ce95b04430e9d77c6bd1df56c7d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231644"
---
# <a name="inputoutput-streams"></a>Input/Output Streams

`basic_iostream`, który jest zdefiniowany w pliku nagłówkowym \<istream> , to szablon klasy dla obiektów, które obsługują zarówno dane wejściowe, jak i wyjściowe strumienie we/wy.

Istnieją dwa definicje typów, które definiują specjalizacje charakterystyczne dla znaków `basic_iostream` i mogą ułatwić odczytywanie kodu: `iostream` (nie należy mylić z plikiem nagłówkowym \<iostream> ) to strumień we/wy, który jest oparty na `basic_iostream<char>` ; `wiostream` to strumień we/wy oparty na `basic_iostream<wchar_t>` .

Aby uzyskać więcej informacji, zobacz [Basic_iostream Class](../standard-library/basic-iostream-class.md), [iostream](../standard-library/basic-iostream-class.md)i [wiostream](../standard-library/basic-iostream-class.md).

Pochodny od `basic_iostream` to szablon klasy `basic_fstream` , który jest używany do przesyłania strumieniowego danych do i z plików.

Istnieją również definicje typów, które zapewniają specjalizację specyficzną dla znaków `basic_fstream` . Są to `fstream` , czyli strumień we/wy pliku oparty na systemie **`char`** , który jest oparty na `wfstream` plikach strumienia we/wy **`wchar_t`** . Aby uzyskać więcej informacji, zobacz [Basic_fstream Class](../standard-library/basic-fstream-class.md), [fstream —](../standard-library/basic-fstream-class.md)i [wfstream](../standard-library/basic-fstream-class.md). Użycie tych elementów typedef wymaga włączenia pliku nagłówkowego \<fstream> .

> [!NOTE]
> Gdy `basic_fstream` obiekt jest używany do wykonywania operacji we/wy na plikach, chociaż bazowy bufor zawiera oddzielnie wskazane położenia do odczytu i zapisu, bieżące wejściowe i bieżące pozycje wyjściowe są powiązane ze sobą, a tym samym, odczytywanie danych przenosi pozycję wyjściową.

Szablon klasy `basic_stringstream` i jego wspólna specjalizacja, `stringstream` są często używane do pracy z obiektami strumienia we/wy w celu wstawiania i wyodrębniania danych znakowych. Aby uzyskać więcej informacji, zobacz [Basic_stringstream Class](../standard-library/basic-stringstream-class.md).

## <a name="see-also"></a>Zobacz też

[stringstream —](../standard-library/basic-stringstream-class.md)\
[Klasa basic_stringstream](../standard-library/basic-stringstream-class.md)\
[\<sstream>](../standard-library/sstream.md)\
[Programowanie iostream](../standard-library/iostream-programming.md)\
[Standardowa biblioteka języka C++](../standard-library/cpp-standard-library-reference.md)

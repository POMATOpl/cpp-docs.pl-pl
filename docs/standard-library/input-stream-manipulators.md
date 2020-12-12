---
description: 'Dowiedz się więcej na temat: manipulowania strumieniem wejściowym'
title: Manipulatory strumieni wejścia
ms.date: 11/04/2016
helpviewer_keywords:
- input streams, manipulators
- input stream objects
ms.assetid: 0addcacb-7b7b-4d70-9775-a59abc400fb3
ms.openlocfilehash: 3da317a9e01652debe0114cfbde284ec0edf6db3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323992"
---
# <a name="input-stream-manipulators"></a>Manipulatory strumieni wejścia

Wiele manipulowania, takich jak [setprecision](../standard-library/iomanip-functions.md#setprecision), jest zdefiniowanych dla `ios` klasy i w związku z tym ma zastosowanie do strumieni wejściowych. Niektóre manipulowania, jednak faktycznie mają wpływ na obiekty strumienia wejściowego. Dla tych, które to najważniejsze, są podstawy manipulowania, `dec` , `oct` , i `hex` , które określają bazę konwersji używaną z liczbami ze strumienia wejściowego.

Przy wyodrębnianiu `hex` Manipulator umożliwia przetwarzanie różnych formatów wejściowych. Na przykład, c, C, 0xC, 0xC, 0Xc i 0XC są interpretowane jako dziesiętna liczba całkowita 12. Dowolny znak inny niż od 0 do 9, od A do F, a do f, x, i X kończy konwersję liczbową. W związku z tym sekwencja `"124n5"` jest konwertowana na liczbę 124 z zestawem bitowym [basic_ios:: Fail](../standard-library/basic-ios-class.md#fail) .

## <a name="see-also"></a>Zobacz też

[Strumienie wejściowe](../standard-library/input-streams.md)

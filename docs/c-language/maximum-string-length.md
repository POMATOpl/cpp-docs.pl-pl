---
description: 'Dowiedz się więcej o: Maksymalna długość ciągu'
title: Maksymalna długość ciągu
ms.date: 11/04/2016
helpviewer_keywords:
- lengths, strings
- string length, maximum
- maximum string length
- strings [C++], length
ms.assetid: 99a80e4a-6212-47b7-a6bd-bdf99bd44928
ms.openlocfilehash: 1da7618a044be2427bd0b0f7f4931287ee4b8014
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243435"
---
# <a name="maximum-string-length"></a>Maksymalna długość ciągu

**Specyficzne dla firmy Microsoft**

Zgodność ze standardem ANSI wymaga, aby kompilator zaakceptował do 509 znaków w literale ciągu po łączeniu. Maksymalna długość literału ciągu dozwolonego w języku Microsoft C wynosi około 2 048 bajtów. Jeśli jednak literał ciągu składa się z części ujętych w znaki podwójnego cudzysłowu, preprocesor łączy części w jeden ciąg, a dla każdej linii łączy, dodaje dodatkowy bajt do całkowitej liczby bajtów.

Na przykład załóżmy, że ciąg składa się z 40 wierszy z 50 znaków na wiersz (2 000 znaków) i jeden wiersz z 7 znakami, a każdy wiersz jest otoczony podwójnym cudzysłowem. Spowoduje to dodanie do 2 007 bajtów i jednego bajtu dla kończącego znaku null, w sumie 2 008 bajtów. Przy łączeniu zostanie dodany dodatkowy znak dla każdego z pierwszych 40 wierszy. To spowoduje całkowite 2 048 bajtów. Należy jednak pamiętać, że jeśli \\ zamiast podwójnych cudzysłowów są używane kontynuacje wiersza (), preprocesor nie dodaje dodatkowego znaku dla każdego wiersza.

Chociaż pojedynczy ciąg w cudzysłowie nie może być dłuższy niż 2048 bajtów, literał ciągu o wartości około 65535 bajtów może być skonstruowany przez złączenie ciągów.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Literały ciągu języka C](../c-language/c-string-literals.md)

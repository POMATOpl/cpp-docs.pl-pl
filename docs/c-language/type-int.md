---
description: 'Dowiedz się więcej na temat: typ int'
title: Typ int
ms.date: 11/04/2016
helpviewer_keywords:
- int data type
- type int
- portability [C++], type int
- signed integers
ms.assetid: 0067ce9a-281e-491a-ae63-632952981e13
ms.openlocfilehash: e6ec94877dad3dd49bb5e9b11f77ceb2a734ab1d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242768"
---
# <a name="type-int"></a>Typ int

Rozmiar **`signed int`** lub **`unsigned int`** element jest standardowym rozmiarem liczby całkowitej na określonym komputerze. Na przykład w 16-bitowych systemach operacyjnych **`int`** Typ ma zwykle 16 bitów lub 2 bajty. W 32-bitowych systemach operacyjnych **`int`** Typ jest zazwyczaj 32 bitów lub 4 bajty. W tym celu **`int`** Typ jest odpowiednikiem albo **`short int`** **`long int`** typu, a **`unsigned int`** Typ jest odpowiednikiem albo **`unsigned short`** **`unsigned long`** typu, w zależności od środowiska docelowego. **`int`** Wszystkie typy reprezentują wartości podpisane, chyba że określono inaczej.

Specyfikatory typu **`int`** i **`unsigned int`** (lub po prostu **`unsigned`** ) definiują niektóre funkcje języka C (na przykład **`enum`** Typ). W takich przypadkach definicje **`int`** i **`unsigned int`** dla konkretnej implementacji określają faktyczny magazyn.

**Specyficzne dla firmy Microsoft**

Oznaczone liczby całkowite są zapisywane w kodzie dopełnień do dwóch. Najbardziej znaczący bit utrzymuje znak: 1 dla wartości ujemnych, 0 dla wartości dodatnich i zera. Zakres wartości jest wyrażony w [limitach liczb całkowitych C i C++](../c-language/cpp-integer-limits.md), które są pobierane z limitów. H plik nagłówkowy.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

> [!NOTE]
> **`int`** **`unsigned int`** Specyfikatory typu i są szeroko stosowane w programach języka C, ponieważ umożliwiają konkretnemu komputerowi obsługę wartości całkowitych w najbardziej efektywny sposób dla tej maszyny. Jednak ponieważ rozmiary **`int`** i **`unsigned int`** są różne, programy, które są zależne od określonego **`int`** rozmiaru mogą nie być przenośne na innych maszynach. Aby programy były bardziej przenośne, można użyć wyrażeń z **`sizeof`** operatorem (jak to opisano w [ `sizeof` operatorze](../c-language/sizeof-operator-c.md)) zamiast zakodowanych rozmiarów danych.

## <a name="see-also"></a>Zobacz też

[Magazyn typów podstawowych](../c-language/storage-of-basic-types.md)

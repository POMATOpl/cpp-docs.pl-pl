---
description: 'Dowiedz się więcej na temat: implementation_only Importowanie atrybutu'
title: implementation_only atrybut importowania
ms.date: 08/29/2019
f1_keywords:
- implementation_only
helpviewer_keywords:
- implementation_only attribute
ms.assetid: d8cabc86-4425-45a0-9587-d57536980088
ms.openlocfilehash: 8afeb9981c5931596fc500419755521a41a3d7c7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236545"
---
# <a name="implementation_only-import-attribute"></a>implementation_only atrybut importowania

**Specyficzne dla języka C++**

Pomija generowanie `.tlh` podstawowego pliku nagłówkowego biblioteki typów.

## <a name="syntax"></a>Składnia

> **#import** **implementation_only** *biblioteki typów*

## <a name="remarks"></a>Uwagi

Ten plik zawiera wszystkie deklaracje używane do ujawniania zawartości biblioteki typów. `.tli`Plik nagłówkowy wraz z implementacjami funkcji składowych otoki zostanie wygenerowany i uwzględniony w kompilacji.

Gdy ten atrybut jest określony, zawartość `.tli` nagłówka znajduje się w tej samej przestrzeni nazw co zazwyczaj jest używana w `.tlh` nagłówku. Ponadto funkcje składowe nie są zadeklarowane jako inline.

Atrybut **implementation_only** jest przeznaczony do użycia w połączeniu z atrybutem [no_implementation](../preprocessor/no-implementation.md) w celu zachowania implementacji z prekompilowanego pliku nagłówkowego (pch). `#import`Instrukcja z `no_implementation` atrybutem jest umieszczana w regionie źródłowym użytym do utworzenia PCH. Wyniki PCH są używane przez wiele plików źródłowych. `#import`Instrukcja z atrybutem **implementation_only** jest następnie używana poza regionem PCH. Musisz użyć tej instrukcji tylko raz w jednym z plików źródłowych. Generuje wszystkie wymagane funkcje składowe otoki bez dodatkowych ponownych kompilacji dla każdego pliku źródłowego.

> [!NOTE]
> Atrybut **implementation_only** w jednej `#import` instrukcji musi być używany w połączeniu z inną `#import` instrukcją o tej samej bibliotece typów z `no_implementation` atrybutem. W przeciwnym razie błędy kompilatora są generowane. Dzieje się tak, ponieważ definicje klas otoki generowane przez `#import` instrukcję z `no_implementation` atrybutem są wymagane do kompilowania implementacji wygenerowanych przez atrybut **implementation_only** .

**ZAKOŃCZENIE specyficzne dla języka C++**

## <a name="see-also"></a>Zobacz też

[Atrybuty #import](../preprocessor/hash-import-attributes-cpp.md)\
[#import — dyrektywa](../preprocessor/hash-import-directive-cpp.md)

---
description: 'Dowiedz się więcej o: hdrstop pragma'
title: hdrstop, pragma
ms.date: 08/29/2019
f1_keywords:
- hdrstop_CPP
- vc-pragma.hdrstop
helpviewer_keywords:
- hdrstop pragma
- pragmas, hdrstop
ms.assetid: 5ea8370a-10d1-4538-ade6-4c841185da0e
ms.openlocfilehash: 1fec99503adfb1d81f7da324db83e4c2b56a3912
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167516"
---
# <a name="hdrstop-pragma"></a>hdrstop, pragma

Zapewnia dodatkową kontrolę nad nazwami plików prekompilacji i w lokalizacji, w której jest zapisywany stan kompilacji.

## <a name="syntax"></a>Składnia

> **#pragma hdrstop** [("*filename*")]

## <a name="remarks"></a>Uwagi

Nazwa *pliku* jest nazwą prekompilowanego pliku nagłówkowego do użycia lub utworzenia (w zależności od tego, czy określono [/Yu](../build/reference/yu-use-precompiled-header-file.md) lub [/YC](../build/reference/yc-create-precompiled-header-file.md) ). Jeśli *Nazwa pliku* nie zawiera specyfikacji ścieżki, zakłada się, że prekompilowany plik nagłówkowy znajduje się w tym samym katalogu, w którym znajduje się plik źródłowy.

Jeśli plik C lub C++ zawiera **hdrstop** pragma podczas kompilowania z `/Yc` , kompilator zapisuje stan kompilacji do lokalizacji dyrektywy pragma. Skompilowany stan dowolnego kodu, który następuje po pragma, nie jest zapisywany.

Użyj nazwy *pliku* , aby nawiązać nazwę prekompilowanego pliku nagłówkowego, w którym jest zapisywany skompilowany stan. Spacja między **hdrstop** i *filename* jest opcjonalna. Nazwa pliku określona w **hdrstop** pragma jest ciągiem i w związku z tym podlega ograniczeniom dowolnego ciągu C lub C++. W szczególności, musisz ująć go w znaki cudzysłowu i używać znaku ucieczki (ukośnik odwrotny), aby określić nazwy katalogów. Na przykład:

```C
#pragma hdrstop( "c:\\projects\\include\\myinc.pch" )
```

Nazwa wstępnie skompilowanego pliku nagłówkowego jest określana zgodnie z następującymi regułami według pierwszeństwa:

1. Argument `/Fp` opcji kompilatora

2. Argument *filename*`#pragma hdrstop`

3. Nazwa podstawowa pliku źródłowego z rozszerzeniem .PCH

W przypadku `/Yc` `/Yu` opcji i, jeśli żadna z dwóch opcji kompilacji ani **hdrstop** pragma nie określa nazwy pliku, podstawowa nazwa pliku źródłowego jest używana jako podstawowa nazwa prekompilowanego pliku nagłówkowego.

Możesz również użyć poleceń przetwarzania wstępnego, aby wykonać makro zastępujące w następujący sposób:

```C
#define INCLUDE_PATH "c:\\progra~`1\\devstsu~1\\vc\\include\\"
#define PCH_FNAME "PROG.PCH"
.
.
.
#pragma hdrstop( INCLUDE_PATH PCH_FNAME )
```

Następujące zasady określają, gdzie można umieścić **hdrstop** pragma:

- Musi znajdować się poza wszelkimi deklaracjami i definicjami danych lub funkcji.

- Musi być określona w pliku źródłowym, a nie w pliku nagłówkowym.

## <a name="example"></a>Przykład

```C
#include <windows.h>                 // Include several files
#include "myhdr.h"

__inline Disp( char *szToDisplay )   // Define an inline function
{
    // ...                           // Some code to display string
}
#pragma hdrstop
```

W tym przykładzie pragma **hdrstop** pojawia się po dołączeniu dwóch plików i zdefiniowaniu wbudowanej funkcji. W pierwszej kolejności może pojawić się nieparzyste położenie dla dyrektywy pragma. Należy jednak wziąć pod uwagę, że przy użyciu opcji ręcznego wstępnej kompilacji `/Yc` i `/Yu` z pragmy **hdrstop** , można wstępnie skompilować całe pliki źródłowe — nawet kod wbudowany. Kompilator Microsoft nie ogranicza do kompilacji wstępnej tylko deklaracji danych.

## <a name="see-also"></a>Zobacz też

[Dyrektywy pragma i słowo kluczowe __pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)

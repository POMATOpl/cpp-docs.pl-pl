---
description: Dowiedz się więcej na temat zmiennych środowiskowych CL
title: Zmienne środowiskowe CL
ms.date: 06/06/2019
helpviewer_keywords:
- INCLUDE environment variable
- cl.exe compiler, environment variables
- LIBPATH environment variable
- environment variables, CL compiler
ms.assetid: 2606585b-a681-42ee-986e-1c9a2da32108
ms.openlocfilehash: 1be95d2c2eddd204846fbcdc8675f28d71c25c0d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179177"
---
# <a name="cl-environment-variables"></a>Zmienne środowiskowe CL

Narzędzie CL używa następujących zmiennych środowiskowych:

- CL i \_ cl_, jeśli zostały zdefiniowane. Narzędzie CL dołącza opcje i argumenty zdefiniowane w zmiennej środowiskowej CL do argumentów wiersza polecenia i dołącza opcje i argumenty zdefiniowane w \_ cl_ przed przetworzeniem.

- Dołącz, który musi wskazywać podkatalog \Include w instalacji programu Visual Studio.

- LIBPATH, który określa katalogi do wyszukiwania plików metadanych, do których odwołuje się [#using](../../preprocessor/hash-using-directive-cpp.md). Aby uzyskać więcej informacji na temat LIBPATH, zobacz [#using](../../preprocessor/hash-using-directive-cpp.md).

Można ustawić \_ zmienną środowiskową CL lub cl_ przy użyciu następującej składni:

> Ustaw CL = [*opcja*]... [*plik*]...] [/link *link-opt* ...] \
> Ustaw \_ CL \_ = [*opcja*]... [*plik*]...] [/link *link-opt* ...]

Aby uzyskać szczegółowe informacje na temat argumentów \_ zmiennych środowiskowych CL i cl_, zobacz [składnia kompilatora MSVC Command-Line](compiler-command-line-syntax.md).

Te zmienne środowiskowe służą do definiowania plików i opcji, których najczęściej używasz. Następnie użyj wiersza polecenia, aby uzyskać więcej plików i opcji do CL do określonych celów. \_Zmienne środowiskowe CL i cl_ są ograniczone do 1024 znaków (limit wprowadzania w wierszu polecenia).

Nie można użyć [/d](d-preprocessor-definitions.md) opcji do zdefiniowania symbolu, który używa znaku równości ( **=** ). Zamiast tego można użyć znaku cyfry ( **#** ) dla znaku równości. W ten sposób można użyć \_ zmiennych środowiskowych CL lub cl_, aby zdefiniować stałe preprocesora z jawnymi wartościami — na przykład, `/DDEBUG#1` Aby zdefiniować `DEBUG=1` .

Aby uzyskać powiązane informacje, zobacz [Ustawianie zmiennych środowiskowych](../setting-the-path-and-environment-variables-for-command-line-builds.md).

## <a name="examples"></a>Przykłady

Następujące polecenie jest przykładem ustawienia zmiennej środowiskowej CL:

> SET CL =/Zp2/OX/I\INCLUDE\MYINCLS \LIB\BINMODE. OBIEKTÓW

Gdy zmienna środowiskowa CL jest ustawiona, po wprowadzeniu `CL INPUT.C` w wierszu polecenia efektywne polecenie zmieni się na:

> CL/Zp2/OX/I\INCLUDE\MYINCLS \LIB\BINMODE. WEJŚCIE OBJ. S

Poniższy przykład powoduje, że polecenie "zwykły CL" kompiluje pliki źródłowe plik1. c i PLIK2. c, a następnie łączy pliki obiektów plik1. obj, PLIK2. obj i FILE3. obj:

> USTAW CL = PLIK1. C PLIK2. S
> Ustaw wartość \_ cl_ = FILE3. Obiektów
> CL

Te zmienne środowiskowe sprawiają, że wywołanie CL ma taki sam skutek jak w przypadku następującego wiersza polecenia:

> CL. C PLIK2. C FILE3. OBIEKTÓW

## <a name="see-also"></a>Zobacz też

[Ustawianie opcji kompilatora](compiler-command-line-syntax.md) \
[Opcje kompilatora MSVC](compiler-options.md)

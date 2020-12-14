---
description: 'Dowiedz się więcej o programie: Określanie pliku wbudowanego'
title: Określanie pliku wbudowanego
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, inline files
- inline files [C++], specifying NMAKE
- files [C++], inline
ms.assetid: 393eccfb-3fc9-4bac-a30c-8ac8d221cca3
ms.openlocfilehash: 461bf507f707512aa690e81dc5752a97d0c1c4ce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224611"
---
# <a name="specifying-an-inline-file"></a>Określanie pliku wbudowanego

W poleceniu należy określić dwa nawiasy kątowe (<<), w którym ma zostać wyświetlona *Nazwa pliku* . Nawiasy kątowe nie mogą być rozwinięciem makra.

## <a name="syntax"></a>Składnia

```
<<[filename]
```

## <a name="remarks"></a>Uwagi

Po uruchomieniu polecenia nawiasy ostre są zamieniane według *nazwy pliku*, jeśli określono lub według unikatowej nazwy wygenerowanej przez NMAKE. Jeśli ta wartość jest określona, *Nazwa pliku* musi być zgodna z nawiasami ostrymi bez spacji lub tabulatora. Ścieżka jest dozwolona. Nie jest wymagane ani nie założono rozszerzenia. Jeśli *Nazwa pliku* jest określona, plik zostanie utworzony w bieżącym lub określonym katalogu, zastępując istniejący plik o tej nazwie; w przeciwnym razie jest tworzony w katalogu TMP (lub bieżącym katalogu, jeśli zmienna środowiskowa TMP nie jest zdefiniowana). Jeśli poprzednia *Nazwa pliku* zostanie ponownie użyta, NMAKE zastępuje poprzedni plik.

## <a name="see-also"></a>Zobacz też

[Pliki wbudowane w pliku reguł programu make](inline-files-in-a-makefile.md)

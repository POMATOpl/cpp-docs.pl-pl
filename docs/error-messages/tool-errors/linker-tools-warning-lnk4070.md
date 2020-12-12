---
description: 'Dowiedz się więcej o: LNK4070 narzędzi KONSOLIDATORA ostrzeżenia narzędzi konsolidatora'
title: Ostrzeżenie LNK4070 narzędzi konsolidatora
ms.date: 11/04/2016
f1_keywords:
- LNK4070
helpviewer_keywords:
- LNK4070
ms.assetid: f95f179a-fff9-427e-bd51-466b3934517f
ms.openlocfilehash: 188c8d88fa4fec332dad80fd5afee346f6099fca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210182"
---
# <a name="linker-tools-warning-lnk4070"></a>Ostrzeżenie LNK4070 narzędzi konsolidatora

/OUT: filename — dyrektywa w. Różnica jest inna niż nazwa pliku wyjściowego "filename"; ignorowanie dyrektywy

`filename`Określony w instrukcji [name](../../build/reference/name-c-cpp.md) lub [Library](../../build/reference/library.md) , gdy plik EXP został utworzony różni się od danych wyjściowych `filename` , które zostały założono domyślnie lub określone przy użyciu opcji [/out](../../build/reference/out-output-file-name.md) .

To ostrzeżenie zostanie wyświetlone, jeśli zmienisz nazwę pliku wyjściowego w środowisku deweloperskim, a plik. def projektu nie został zaktualizowany. Ręcznie zaktualizuj plik. def, aby rozwiązać to ostrzeżenie.

Program kliencki, który używa uzyskanej biblioteki DLL, może napotkać problemy.

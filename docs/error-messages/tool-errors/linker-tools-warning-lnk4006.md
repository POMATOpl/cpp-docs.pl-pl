---
description: 'Dowiedz się więcej o: LNK4006 narzędzi KONSOLIDATORA ostrzeżenia narzędzi konsolidatora'
title: Ostrzeżenie LNK4006 narzędzi konsolidatora
ms.date: 11/04/2016
f1_keywords:
- LNK4006
helpviewer_keywords:
- LNK4006
ms.assetid: 3a637d17-1676-4ea6-bd8b-290137d28d3b
ms.openlocfilehash: 526b3f380ef7e05448280094f360c145d7f21c04
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332009"
---
# <a name="linker-tools-warning-lnk4006"></a>Ostrzeżenie LNK4006 narzędzi konsolidatora

symbol jest już zdefiniowany w obiekcie; Druga Definicja została zignorowana

Podany `symbol` , wyświetlany w jego postaci dekoracyjnej, został wielokrotnie zdefiniowany. Po napotkaniu tego ostrzeżenia `symbol` zostanie dodane dwa razy, ale zostanie użyty tylko jego pierwszy formularz.

To ostrzeżenie można uzyskać, jeśli próbujesz scalić dwa libs importowania w jeden.

W przypadku ponownego kompilowania biblioteki wykonawczej C można zignorować ten komunikat.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aby rozwiązać ten problem, można użyć następujących rozwiązań

1. Dana wartość `symbol` może być spakowaną funkcją, utworzoną przez kompilację z [/Gy](../../build/reference/gy-enable-function-level-linking.md). Ten symbol został uwzględniony w więcej niż jednym pliku, ale został zmieniony między kompilacjami. Skompiluj ponownie wszystkie pliki, które zawierają `symbol` .

1. Dane `symbol` mogą zostać zdefiniowane inaczej w dwóch obiektach Członkowskich w różnych bibliotekach.

1. Wartość bezwzględna może być zdefiniowana dwa razy, z inną wartością w każdej definicji.

1. Jeśli komunikat o błędzie jest odbierany podczas łączenia bibliotek, `symbol` istnieje już w bibliotece dodawanej do programu.

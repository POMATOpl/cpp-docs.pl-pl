---
description: 'Dowiedz się więcej na temat: znaki specjalne w pliku reguł programu make'
title: Znaki specjalne w pliku reguł programu Make
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, special characters
- makefiles, special characters
- special characters, in NMAKE macros
- macros, special characters
ms.assetid: 92c34ab5-ca6b-4fc0-bcf4-3172eaeda9f0
ms.openlocfilehash: 22b8f6dd82191c88a23eaf1dabb551d468293a42
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224676"
---
# <a name="special-characters-in-a-makefile"></a>Znaki specjalne w pliku reguł programu Make

Aby użyć znaku specjalnego NMAKE jako znaku literału, umieść karetkę (^) przed nim. NMAKE ignoruje karetkę poprzedzającą inne znaki. Znaki specjalne, których dotyczy problem:

`:  ;  #  (  )  $  ^  \  {  }  !  @  —`

Daszek (^) w ciągu ujętym w cudzysłów jest traktowany jako literał znaku karetki. Karetka na końcu linii wstawia literałowy znak nowego wiersza w ciągu lub makro.

W makrach ukośnik odwrotny ( \\ ), po którym następuje znak nowego wiersza, jest zastępowany spacją.

W poleceniach, symbol procentu (%) jest specyfikatorem pliku. Aby reprezentować% dosłownie w poleceniu, określ podwójny znak procentu (%%) zamiast jednego. W innych sytuacjach NMAKE interpretuje pojedynczy element% dosłownie, ale zawsze interpretuje podwójny%% jako pojedynczy procent. W związku z tym, aby reprezentować literał%%, należy określić trzy znaki procentowe,%%% lub cztery znaki procentowe,%%%%.

Aby użyć znaku dolara ($) jako literału w poleceniu, należy określić dwa znaki dolara ($ $). Tej metody można również użyć w innych sytuacjach, gdzie ^ $ działa.

## <a name="see-also"></a>Zobacz też

[Zawartość pliku reguł programu make](contents-of-a-makefile.md)

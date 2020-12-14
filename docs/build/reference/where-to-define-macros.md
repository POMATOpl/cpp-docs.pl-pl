---
description: 'Dowiedz się więcej o programie: gdzie definiować makra'
title: Miejsce definiowania makr
ms.date: 11/04/2016
helpviewer_keywords:
- defining macros
- macros, NMAKE
- NMAKE program, defining macros
ms.assetid: 0fc59ec5-5f58-4644-b7da-7b021f7001af
ms.openlocfilehash: b5fc7d6e1fd8247816993929791bf734596d00e6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259204"
---
# <a name="where-to-define-macros"></a>Miejsce definiowania makr

Zdefiniuj makra w wierszu polecenia, pliku poleceń, programie Make lub pliku Tools.ini.

W pliku reguł programu make lub Tools.ini każda definicja makra musi znajdować się w osobnym wierszu i nie może zaczynać się od spacji lub tabulatora. Spacje lub tabulatory wokół znaku równości są ignorowane. Wszystkie [znaki ciągu](defining-an-nmake-macro.md) są literałem, włącznie z otaczającymi je cudzysłowami i spacjami osadzonymi.

W wierszu polecenia lub pliku poleceń, spacje i tabulatory oddzielają argumenty i nie mogą otaczać znaku równości. Jeśli `string` zawiera osadzone spacje lub tabulatory, należy ująć ciąg albo całe makro w podwójny cudzysłów ("").

## <a name="see-also"></a>Zobacz też

[Definiowanie makra NMAKE](defining-an-nmake-macro.md)

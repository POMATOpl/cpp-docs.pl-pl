---
description: Dowiedz się więcej na temat:/DYNAMICBASE
title: /DYNAMICBASE
ms.date: 06/12/2018
f1_keywords:
- /dynamicbase
helpviewer_keywords:
- -DYNAMICBASE editbin option
- DYNAMICBASE editbin option
- /DYNAMICBASE editbin option
ms.assetid: edb3df90-7b07-42fb-a94a-f5a4c1d325d6
ms.openlocfilehash: 289c0591fa6989d235a63b9bef249078f9a11174
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201056"
---
# <a name="dynamicbase"></a>/DYNAMICBASE

Określa, czy generować obraz wykonywalny, który może być losowo zmieniany w czasie ładowania przy użyciu funkcji losowego układu przestrzeni adresowej (ASLR) systemu Windows, która była początkowo dostępna w systemie Windows Vista.

## <a name="syntax"></a>Składnia

> **/DYNAMICBASE**[**: No**]

## <a name="remarks"></a>Uwagi

Opcja **/DYNAMICBASE** modyfikuje nagłówek *obrazu wykonywalnego*, pliku DLL lub exe, aby wskazać, czy aplikacja powinna być losowo zmieniana w czasie ładowania, i umożliwia losowe generowanie alokacji adresów wirtualnych, co ma wpływ na lokalizację pamięci wirtualnej sterty, stosy i inne alokacje systemu operacyjnego. Opcja **/DYNAMICBASE** dotyczy zarówno obrazów 32-bitowych, jak i 64-bitowych. ASLR jest obsługiwana w systemach operacyjnych Windows Vista i nowszych. Ta opcja jest ignorowana przez wcześniejsze systemy operacyjne.

Domyślnie **/DYNAMICBASE** jest włączona. Aby wyłączyć tę opcję, użyj **/DYNAMICBASE: No**. Opcja **/DYNAMICBASE** jest wymagana, aby opcja [/HIGHENTROPYVA](highentropyva-support-64-bit-aslr.md) miała efekt.

## <a name="see-also"></a>Zobacz też

- [Opcje polecenia EDITBIN](editbin-options.md)
- [Ochrona przed oprogramowaniem ISV systemu Windows](/previous-versions/bb430720(v=msdn.10))

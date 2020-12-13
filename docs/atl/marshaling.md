---
description: 'Dowiedz się więcej o: kierowanie'
title: Marshaling
ms.date: 11/04/2016
helpviewer_keywords:
- marshaling, COM interop
- marshaling
- COM interfaces, marshaling
ms.assetid: 40644b0a-1106-4fc8-9dfb-9bee9915d825
ms.openlocfilehash: 2931bd9ab5e2fb8376ced44dd519a6de107be88e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152636"
---
# <a name="marshaling"></a>Marshaling

Technika COM kierująca umożliwia interfejsy uwidocznione przez obiekt w jednym procesie, który ma być używany w innym procesie. W obszarze kierowanie COM udostępnia kod (lub używa kodu dostarczonego przez implementujący interfejs) zarówno do pakowania parametrów metody do formatu, który może być przenoszony między procesami (a także przez sieć do procesów uruchomionych na innych maszynach) oraz do rozpakowywania tych parametrów na drugim końcu. Analogicznie, COM musi wykonać te same kroki na zwracaniu z wywołania.

> [!NOTE]
> Kierowanie nie jest zwykle konieczne, gdy interfejs dostarczony przez obiekt jest używany w tym samym procesie co obiekt. Jednak może być wymagana kierowanie między wątkami.

## <a name="see-also"></a>Zobacz też

[Wprowadzenie do modelu COM](../atl/introduction-to-com.md)<br/>
[Szczegóły organizowania](/windows/win32/com/marshaling-details)

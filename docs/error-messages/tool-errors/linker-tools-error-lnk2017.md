---
description: 'Dowiedz się więcej na temat: Błąd narzędzi konsolidatora LNK2017'
title: Błąd narzędzi konsolidatora LNK2017
ms.date: 11/04/2016
f1_keywords:
- LNK2017
helpviewer_keywords:
- LNK2017
ms.assetid: f7c21733-b0fb-4888-a295-9b453ba6ee77
ms.openlocfilehash: e4215d7c1730f85f43c2440163fa03ad97c741e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338443"
---
# <a name="linker-tools-error-lnk2017"></a>Błąd narzędzi konsolidatora LNK2017

przemieszczenie "symbol" do "segment" jest nieprawidłowe bez/LARGEADDRESSAWARE: NO

Próbujesz utworzyć obraz 64-bitowy z 32-bitowymi adresami. W tym celu należy wykonać następujące czynności:

- Użyj stałego adresu ładowania.

- Ogranicz obraz do 3 GB.

- Określ [/LARGEADDRESSAWARE: No](../../build/reference/largeaddressaware-handle-large-addresses.md).

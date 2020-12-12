---
description: 'Dowiedz się więcej na temat: Błąd narzędzi konsolidatora LNK1241'
title: Błąd narzędzi konsolidatora LNK1241
ms.date: 11/04/2016
f1_keywords:
- LNK1241
helpviewer_keywords:
- LNK1241
ms.assetid: 7b8b52eb-0231-4521-b52a-2bce8d3e8956
ms.openlocfilehash: abc72b70af9ab694744a91a8789207055bd1a5bb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193932"
---
# <a name="linker-tools-error-lnk1241"></a>Błąd narzędzi konsolidatora LNK1241

plik zasobu "plik zasobów" został już określony

Ten błąd jest generowany, gdy uruchamiasz **CVTRES** ręcznie z wiersza polecenia, a następnie przekażesz otrzymany plik. obj do konsolidatora oprócz innych plików. res.

Aby określić wiele plików. res, przekaż je wszystkie do konsolidatora jako pliki. res, a nie z plików. obj utworzonych przez **CVTRES**.

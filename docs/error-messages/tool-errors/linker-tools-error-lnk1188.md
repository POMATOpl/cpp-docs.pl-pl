---
description: 'Dowiedz się więcej na temat: Błąd narzędzi konsolidatora LNK1188'
title: Błąd narzędzi konsolidatora LNK1188
ms.date: 11/04/2016
f1_keywords:
- LNK1188
helpviewer_keywords:
- LNK1188
ms.assetid: 4af574b0-5b41-4580-9a37-52a634add995
ms.openlocfilehash: 1bd826c3734d8079b370712ae829a0d0fb1abded
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321842"
---
# <a name="linker-tools-error-lnk1188"></a>Błąd narzędzi konsolidatora LNK1188

BADFIXUPSECTION:: nieprawidłowy cel naprawy "symbol"; dozwolona sekcja o zerowej długości

W ramach linku VxD element docelowy relokacji nie ma sekcji. W przypadku LINK386 (starszej wersji) rekord grupy OMF (wygenerowany przez dyrektywę grupy MASM) mógł zostać użyty do połączenia sekcji o zerowej długości z inną sekcją o niezerowej długości. Format COFF nie obsługuje dyrektywy GROUP i sekcji o zerowej długości. Gdy LINK automatycznie konwertuje ten typ obiektów OMF na COFF, ten błąd może wystąpić.

---
description: 'Dowiedz się więcej na temat: błąd krytyczny NMAKE U1051'
title: Błąd krytyczny NMAKE U1051
ms.date: 11/04/2016
f1_keywords:
- U1051
helpviewer_keywords:
- U1051
ms.assetid: fede5cd5-dac3-47b7-b86d-e1acfb78699f
ms.openlocfilehash: c7d465eaf34adb69e41f523006fb0740eea722ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272113"
---
# <a name="nmake-fatal-error-u1051"></a>Błąd krytyczny NMAKE U1051

za mało pamięci

NMAKE zabrakło pamięci, w tym pamięci wirtualnej, ponieważ plik reguł programu make jest zbyt duży lub skomplikowany.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aby rozwiązać ten problem, można użyć następujących rozwiązań

1. Zwolnij trochę miejsca na dysku.

1. Zwiększ rozmiar pliku stronicowania systemu Windows NT lub pliku wymiany systemu Windows.

1. Jeśli jest używana tylko część pliku reguł programu make, należy podzielić plik reguł programu make na osobne pliki **lub użyć go. W przypadku** wstępnego przetwarzania dyrektyw w celu ograniczenia ilości, którą NMAKE musi przetworzyć. **! Jeśli** dyrektywy obejmują **! Jeśli**, `!IFDEF` , **! IFNDEF**, **! ELSE IF**, **! ELSE** `IFDEF` i **! ELSE** `IFNDEF` .

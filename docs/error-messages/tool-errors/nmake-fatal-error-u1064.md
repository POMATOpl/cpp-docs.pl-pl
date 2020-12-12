---
description: 'Dowiedz się więcej na temat: błąd krytyczny NMAKE U1064'
title: Błąd krytyczny NMAKE U1064
ms.date: 11/04/2016
f1_keywords:
- U1064
helpviewer_keywords:
- U1064
ms.assetid: 7141e66e-cde6-4173-84df-a391f3ebcdd1
ms.openlocfilehash: 881c93eca4efad064dff633bbde34dc88e71345e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330368"
---
# <a name="nmake-fatal-error-u1064"></a>Błąd krytyczny NMAKE U1064

Nie znaleziono pliku reguł programu make i nie określono elementu docelowego

W wierszu polecenia NMAKE nie określono pliku reguł programu make lub elementu docelowego, a bieżący katalog nie zawiera plik o nazwie make.

NMAKE wymaga pliku reguł programu make lub wiersza polecenia (lub obu tych opcji). Aby udostępnić plik reguł programu make NMAKE, należy określić opcję/F lub umieścić w bieżącym katalogu pliku o nazwie reguł programu make. NMAKE może utworzyć obiekt docelowy wiersza polecenia za pomocą reguły wnioskowania, jeśli nie podano pliku reguł programu make.

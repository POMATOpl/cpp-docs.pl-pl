---
description: 'Dowiedz się więcej na temat: jak BSCMAKE kompiluje. Plik BSC'
title: W jaki sposób BSCMAKE kompiluje plik .Bsc
ms.date: 11/04/2016
helpviewer_keywords:
- browse information files (.bsc), building
ms.assetid: 8512b33e-c856-44a2-87bd-01ab10b52a95
ms.openlocfilehash: 6d468f365f7f42be2eb393e53d72053b682ec65a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191384"
---
# <a name="how-bscmake-builds-a-bsc-file"></a>W jaki sposób BSCMAKE kompiluje plik .Bsc

BSCMAKE kompiluje lub odtwarza plik. bsc w najbardziej wydajny sposób. Aby uniknąć potencjalnych problemów, ważne jest zrozumienie procesu kompilacji.

Gdy BSCMAKE kompiluje plik informacji o przeglądaniu, obcina pliki. sbr do zerowej długości. Podczas kolejnej kompilacji tego samego pliku o zerowej długości (lub pustej) plik SBR informuje BSCMAKE, że plik. sbr nie ma żadnego nowego wkładu do wykonania. Pozwala BSCMAKE wiedzieć, że aktualizacja tej części pliku nie jest wymagana, a przyrostowa kompilacja będzie wystarczająca. Podczas każdej kompilacji (jeśli nie określono opcji/n) BSCMAKE najpierw próbuje zaktualizować plik przyrostowo, używając tylko plików. sbr, które uległy zmianie.

BSCMAKE szuka pliku. bsc, który ma nazwę określoną przy użyciu/o opcji. Jeśli/o nie zostanie określony, BSCMAKE szuka pliku, który ma podstawową nazwę pierwszego pliku. sbr i rozszerzenie. BSC. Jeśli plik istnieje, BSCMAKE wykonuje przyrostową kompilację pliku informacji o przeglądaniu przy użyciu tylko plików współautora. sbr. Jeśli plik nie istnieje, BSCMAKE wykonuje pełną kompilację przy użyciu wszystkich plików. sbr. Reguły dla kompilacji są następujące:

- Aby pełna kompilacja powiodła się, wszystkie określone pliki. sbr muszą istnieć i nie mogą być obcinane. Jeśli plik. sbr zostanie obcięty, należy go ponownie skompilować (przez ponowną kompilację lub asembler) przed uruchomieniem BSCMAKE.

- Aby kompilacja przyrostowa zakończyła się powodzeniem, musi istnieć plik. BSC. Wszystkie pliki. sbr, nawet puste pliki, muszą istnieć i muszą być określone w wierszu polecenia BSCMAKE. Jeśli pominięto plik. sbr z wiersza polecenia, BSCMAKE usuwa jego udział z pliku.

## <a name="see-also"></a>Zobacz też

[Kompilowanie. Plik BSC](building-a-dot-bsc-file.md)

---
description: Dowiedz się więcej na temat:/GUARD (Włączanie testów ochrony)
title: /GUARD (włączenie sprawdzeń za pomocą wyrażenia Guard)
ms.date: 11/04/2016
ms.assetid: 72758e23-70ac-4616-94d7-d767477406d1
ms.openlocfilehash: 4f76de815bc10f8e1203510b25b237fe8db93444
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191722"
---
# <a name="guard-enable-guard-checks"></a>/GUARD (włączenie sprawdzeń za pomocą wyrażenia Guard)

Określa obsługę kontroli ochrony przepływu sterowania w obrazie wykonywalnym.

## <a name="syntax"></a>Składnia

```
/GUARD:{CF|NO}
```

## <a name="remarks"></a>Uwagi

Gdy jest określony/GUARD: CF, konsolidator modyfikuje nagłówek pliku. dll lub. exe, aby wskazać obsługę testów środowiska uruchomieniowego ochrony przepływu sterowania (CFG). Konsolidator dodaje również wymagane dane adresu docelowego przepływu sterowania do nagłówka. Domyślnie/GUARD: CF jest wyłączone. Można ją jawnie wyłączyć przy użyciu/GUARD: NO. Aby była skuteczna,/GUARD: CF również wymaga opcji konsolidatora [/DYNAMICBASE (Użyj losowo układu przestrzeni adresowej)](dynamicbase-use-address-space-layout-randomization.md) , która jest domyślnie włączona.

Gdy kod źródłowy jest kompilowany przy użyciu opcji [/Guard: CF](guard-enable-control-flow-guard.md) , kompilator analizuje przepływ sterowania, sprawdzając wszystkie wywołania pośrednie dla możliwych adresów docelowych. Kompilator wstawia kod, aby sprawdzić, czy adres docelowy instrukcji wywołania pośredniego znajduje się na liście znanych adresów docelowych w czasie wykonywania. Systemy operacyjne obsługujące CFG zatrzymują program, który nie może sprawdzić, czy środowisko uruchomieniowe CFG zostało wykonane. Utrudnia to osobie atakującej wykonywanie złośliwego kodu przy użyciu uszkodzenia danych w celu zmiany celu wywołania.

Aby można było tworzyć obrazy wykonywalne z obsługą CFG, należy określić opcję/GUARD: CF zarówno do kompilatora, jak i konsolidatora. Kod skompilowany, ale niepołączony za pomocą/GUARD: CF ponosi koszt kontroli środowiska uruchomieniowego, ale nie włącza ochrony CFG. Gdy opcja/GUARD: CF jest określona dla `cl` polecenia do kompilowania i łączenia w jednym kroku, kompilator przekazuje flagę do konsolidatora. Gdy w programie Visual Studio jest ustawiona właściwość **Ochrona przepływu sterowania** ,/Guard: CF opcja jest przenoszona do kompilatora i konsolidatora. Gdy pliki lub biblioteki obiektów zostały skompilowane oddzielnie, opcja musi być jawnie określona w `link` poleceniu.

### <a name="to-set-this-linker-option-in-visual-studio"></a>Aby ustawić tę opcję konsolidatora w programie Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać więcej informacji, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Rozwiń węzeł **Właściwości konfiguracji**, **konsolidator**, **wiersz polecenia**.

1. W obszarze **Opcje dodatkowe** wprowadź `/GUARD:CF` .

## <a name="see-also"></a>Zobacz też

[/guard (włącz ochronę przepływu sterowania)](guard-enable-control-flow-guard.md)<br/>
[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)

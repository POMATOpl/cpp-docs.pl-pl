---
description: 'Dowiedz się więcej na temat: używanie kompilacji debugowania do sprawdzania zastępowania pamięci'
title: Korzystanie z kompilacji debugowania do sprawdzania nadpisywania pamięci
ms.date: 11/04/2016
helpviewer_keywords:
- memory, overwrites
ms.assetid: 1345eb4d-24ba-4595-b1cc-2da66986311e
ms.openlocfilehash: 03981696a0314632aebb959d6fa1d986145c087c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199067"
---
# <a name="using-the-debug-build-to-check-for-memory-overwrite"></a>Korzystanie z kompilacji debugowania do sprawdzania nadpisywania pamięci

Aby użyć kompilacji debugowania do sprawdzenia zastąpienia pamięci, należy najpierw skompilować projekt w celu debugowania. Następnie przejdź do początku `InitInstance` funkcji aplikacji i Dodaj następujący wiersz:

```
afxMemDF |= checkAlwaysMemDF;
```

Program przydzielający pamięć programu Debug umieszcza w bajtach ochronę wszystkich alokacji pamięci. Jednak te bajty Guard nie wykonują żadnych dobrych, chyba że sprawdzisz, czy zostały zmienione (co wskazuje na zastępowanie pamięci). W przeciwnym razie jest to tylko bufor, który może w rzeczywistości pozwolić na zastępowanie pamięci.

Włączając `checkAlwaysMemDF` , wymusimy, aby MFC wykonał wywołanie `AfxCheckMemory` funkcji za każdym razem, gdy wywołanie **`new`** lub **`delete`** zostanie wykonane. W przypadku wykrycia zastępowania pamięci zostanie wygenerowany komunikat śledzenia podobny do następującego:

```
Damage Occurred! Block=0x5533
```

Jeśli zobaczysz jeden z tych komunikatów, musisz przejść przez swój kod, aby określić, gdzie wystąpił uszkodzenie. Aby wyizolować dokładniejsze miejsce zastępowania pamięci, można wykonać jawne wywołania do `AfxCheckMemory` siebie. Na przykład:

```
ASSERT(AfxCheckMemory());
    DoABunchOfStuff();
    ASSERT(AfxCheckMemory());
```

Jeśli pierwsze potwierdzenie powiedzie się, a druga nie powiedzie się, oznacza to, że zastępowanie pamięci musi wystąpić w funkcji między dwoma wywołaniami.

W zależności od charakteru aplikacji może się okazać, że `afxMemDF` program uruchamia zbyt wolno, aby testy były nawet niewolniejsze. `afxMemDF`Zmienna powoduje `AfxCheckMemory` wywoływanie dla każdego wywołania do New i DELETE. W takim przypadku należy wyrównać własne wywołania do `AfxCheckMemory` (), jak pokazano powyżej, i spróbować wyizolować zastępowanie pamięci w ten sposób.

## <a name="see-also"></a>Zobacz też

[Rozwiązywanie problemów z kompilacją wersji](fixing-release-build-problems.md)

---
description: 'Dowiedz się więcej o programie: redystrybuuj Visual C++ kontrolki ActiveX'
title: Redystrybuowanie formantów ActiveX programu Visual C++
ms.date: 11/04/2016
helpviewer_keywords:
- controls [C++], redistributing
- controls [C++], distributing
ms.assetid: eefbb7e4-d28c-4c35-98bf-d9540cfaae83
ms.openlocfilehash: 4960af93b140e883ff50f6ff81824cd9e67d44f6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247348"
---
# <a name="redistributing-visual-c-activex-controls"></a>Redystrybuowanie formantów ActiveX programu Visual C++

Visual C++ 6,0 dostarcza kontrolki ActiveX, których można używać w aplikacjach, które są następnie ponownie dystrybuowane. Te kontrolki nie są już zawarte w Visual C++. Zgodnie z umowami licencyjnymi dotyczącymi Visual C++ 6,0 można ponownie rozesłać te kontrolki za pomocą aplikacji utworzonych w Visual C++.

> [!NOTE]
> Visual C++ 6,0 nie jest już obsługiwany przez firmę Microsoft.

Aby zapoznać się z listą formantów ActiveX pakietu redystrybucyjnego Visual C++ 6,0, zobacz Common\Redist\Redist.txt na dysku 1 z dysku CD produktu Visual C++ 6,0.

Podczas dystrybucji aplikacji należy zainstalować i zarejestrować. ocx dla kontrolki ActiveX (przy użyciu Regsvr32.exe). Ponadto należy upewnić się, że komputer docelowy ma aktualne wersje następujących plików systemowych (gwiazdka wskazuje, że plik musi być zarejestrowany):

- Asycfilt.dll

- Comcat.dll \*

- Oleaut32.dll \*

- Olepro32.dll \*

- Stdole2. tlb

Jeśli te biblioteki DLL nie są dostępne w systemie docelowym, należy je zaktualizować przy użyciu zalecanego mechanizmu do aktualizowania odpowiedniego systemu operacyjnego. Najnowsze dodatki Service Pack dla systemów operacyjnych Windows można pobrać z programu [http://windowsupdate.microsoft.com](https://windowsupdate.microsoft.com) .

W przypadku korzystania z formantu ActiveX, który łączy się z bazą danych, należy również replikować nazwę źródła danych na komputerze docelowym. Można to zrobić programowo przy użyciu funkcji, takich jak `ConfigDSN` .

Niektóre redystrybucyjne kontrolki ActiveX mają dodatkowe zależności. Dla każdego pliku ocx znajdującego się w folderze Os\System na dysku CD produktu Visual C++ 6,0 istnieje również plik. DEP. Dla każdego pliku ocx, który ma zostać ponownie rozdystrybuowany, poszukaj jednego lub większej liczby wpisów w odpowiednim pliku DEP. Jeśli plik znajduje się na liście, należy się upewnić, że plik znajduje się na komputerze docelowym. Wszystkie biblioteki dll bezpośrednio obsługujące plik ocx muszą być zarejestrowane. (Aby Regsvr32.exe się powieść, komputer docelowy musi najpierw zawierać wszystkie biblioteki DLL, które formant statycznie ładuje.) Ponadto jeśli biblioteka DLL, która jest wymieniona jako zależność, również zawiera plik. DEP w folderze Os\System na dysku CD Visual C++ 6,0, należy również sprawdzić, czy plik DEP służy do korzystania z wpisów.

## <a name="see-also"></a>Zobacz też

[Ponowne dystrybuowanie plików programu Visual C++](redistributing-visual-cpp-files.md)

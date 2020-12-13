---
description: Dowiedz się więcej o:/ZF (szybsze generowanie plików PDB)
title: /Zf (Szybsze generowanie pliku PDB)
ms.date: 03/29/2018
f1_keywords:
- /Zf
helpviewer_keywords:
- /Zf
- -Zf
ms.openlocfilehash: 6acf84de3c286131f470808505cdf0e895feeaeb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97178891"
---
# <a name="zf-faster-pdb-generation"></a>/Zf (Szybsze generowanie pliku PDB)

Włącz szybszą generację plików PDB w kompilacjach równoległych przez zminimalizowanie wywołań RPC do mspdbsrv.exe.

## <a name="syntax"></a>Składnia

> **/ZF**

## <a name="remarks"></a>Uwagi

Opcja **/ZF** umożliwia obsługę kompilatora w przypadku szybszej generacji plików PDB przy użyciu opcji [/MP (kompilacja z wieloma procesami)](mp-build-with-multiple-processes.md) lub w przypadku, gdy system kompilacji (na przykład [MSBuild](/visualstudio/msbuild/msbuild-reference) lub [CMAKE](../cmake-projects-in-visual-studio.md)) może uruchamiać wiele cl.exe procesów kompilatora jednocześnie. Ta opcja powoduje, że funkcja kompilatora opóźni generowanie indeksów typu dla każdego rekordu typu w pliku PDB do momentu zakończenia kompilacji, a następnie żąda ich wszystkich w pojedynczym wywołaniu wywołania RPC do mspdbsrv.exe, zamiast wykonywania żądania RPC dla każdego rekordu. Może to znacznie zwiększyć przepływność kompilacji, zmniejszając obciążenie RPC w procesie mspdbsrv.exe w środowisku, w którym wiele procesów kompilatora cl.exe uruchamiane jednocześnie.

Ponieważ opcja **/ZF** dotyczy tylko generacji plików PDB, wymaga opcji [/Zi](z7-zi-zi-debug-information-format.md) lub [/Zi](z7-zi-zi-debug-information-format.md) .

Opcja **/ZF** jest dostępna począwszy od programu Visual Studio 2017 w wersji 15,1, gdzie jest domyślnie wyłączona. Począwszy od programu Visual Studio 2017 w wersji 15,7 Preview 3, ta opcja jest domyślnie włączona po włączeniu opcji **/Zi** lub **/Zi** .

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz   >  stronę właściwości konfiguracja wiersza polecenia **C/C++**  >   .

1. Zmodyfikuj właściwość **Opcje dodatkowe** , aby obejmowała **/ZF** , a następnie wybierz **przycisk OK**.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora w porządku alfabetycznym](compiler-options-listed-alphabetically.md)<br/>
[/MP (kompilacja z wieloma procesami)](mp-build-with-multiple-processes.md)<br/>

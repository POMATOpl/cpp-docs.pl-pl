---
description: Dowiedz się więcej o:/FS (Wymuś synchroniczne zapisy PDB)
title: /FS (Wymuś synchroniczne zapisy do bazy PDB)
ms.date: 11/04/2016
f1_keywords:
- /FS
helpviewer_keywords:
- -FS compiler option [C++]
- /FS compiler option [C++]
ms.assetid: b2caaffe-f6e1-4963-b068-648f06b105e0
ms.openlocfilehash: 2dcddd046cc7232f40be5a54d73e659ed099e85d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192034"
---
# <a name="fs-force-synchronous-pdb-writes"></a>/FS (Wymuś synchroniczne zapisy do bazy PDB)

Wymusza zapis do pliku bazy danych programu (PDB) — utworzonego przez [/Zi](z7-zi-zi-debug-information-format.md) lub [/Zi](z7-zi-zi-debug-information-format.md)— do serializacji za pomocą MSPDBSRV.EXE.

## <a name="syntax"></a>Składnia

```
/FS
```

## <a name="remarks"></a>Uwagi

Domyślnie, gdy jest określony **/Zi** lub **/Zi** , kompilator blokuje pliki PDB, aby zapisywać informacje o typie i symboliczne informacje o debugowaniu. Może to znacząco skrócić czas, przez jaki kompilator generuje informacje o typie, gdy liczba typów jest duża. Jeśli inny proces tymczasowo blokuje plik PDB — na przykład program antywirusowy — zapis w kompilatorze może zakończyć się niepowodzeniem i może wystąpić błąd krytyczny. Ten problem może również wystąpić, gdy wiele kopii cl.exe uzyskać dostęp do tego samego pliku PDB — na przykład jeśli rozwiązanie ma niezależne projekty, które używają tych samych katalogów pośrednich lub katalogów wyjściowych, a kompilacje równoległe są włączone. Opcja kompilatora **/FS** uniemożliwia kompilatorowi zablokowanie pliku PDB i wymuszenie zapisu do przechodzenia przez MSPDBSRV.EXE, który serializować dostęp. Może to znacznie wydłużyć kompilacje i nie uniemożliwia wszystkich błędów, które mogą wystąpić, gdy wiele wystąpień cl.exe dostępu do pliku PDB w tym samym czasie. Zalecamy zmianę rozwiązania tak, aby niezależne projekty zapisu w oddzielnych lokalizacjach pośrednich i wyjściowych, lub że jeden z projektów zależy od innych, aby wymusić kompilacje serializowanych projektów.

Opcja [/MP](mp-build-with-multiple-processes.md) domyślnie włącza **/FS** .

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz folder **C/C++** .

1. Wybierz stronę właściwości **wiersza polecenia** .

1. Zmodyfikuj właściwość **Opcje dodatkowe** , aby uwzględnić `/FS` , a następnie wybierz przycisk **OK**.

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)

---
description: Dowiedz się więcej na temat:/WL (Włączanie diagnostyki One-Line)
title: /WL (Włącz diagnostykę w trybie on-line)
ms.date: 11/04/2016
f1_keywords:
- /wl
helpviewer_keywords:
- -WL compiler option [C++]
- /WL compiler option [C++]
- WL compiler option [C++]
ms.assetid: 332cadb4-8ea6-45fe-b67d-33ddec1f2c2e
ms.openlocfilehash: 032f2c41558c1475be5673d4a69de9ff9b09f323
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258866"
---
# <a name="wl-enable-one-line-diagnostics"></a>/WL (Włącz diagnostykę w trybie on-line)

Dołącza dodatkowe informacje do błędu lub komunikatu ostrzegawczego.

## <a name="syntax"></a>Składnia

```
/WL
```

## <a name="remarks"></a>Uwagi

Do komunikatów o błędach i ostrzeżeniach kompilatora języka C++ mogą występować dodatkowe informacje, które domyślnie pojawiają się w nowym wierszu. Podczas kompilowania z wiersza polecenia dodatkowy wiersz informacji może być dołączany do komunikatu o błędzie lub ostrzeżenie. Może to być pożądane, jeśli przechwytujesz dane wyjściowe kompilacji do pliku dziennika, a następnie przetworzysz ten dziennik w celu znalezienia wszystkich błędów i ostrzeżeń. Średnik będzie oddzielał błąd lub komunikat ostrzegawczy od dodatkowego wiersza.

Nie wszystkie komunikaty o błędach i ostrzeżeniach zawierają dodatkową linię informacji. Poniższy kod generuje błąd, który zawiera dodatkową linię informacji; umożliwia przetestowanie efektu przy użyciu **/WL**.

```cpp
// compiler_option_WL.cpp
// compile with: /WL
#include <queue>
int main() {
   std::queue<int> q;
   q.fromthecontinuum();   // C2039
}
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **C/C++** .

1. Kliknij stronę właściwości **wiersza polecenia** .

1. Wpisz opcję kompilatora w polu **dodatkowe opcje** .

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)

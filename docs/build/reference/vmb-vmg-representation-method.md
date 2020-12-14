---
description: Dowiedz się więcej o:/VMB,/VMG (Metoda reprezentacji)
title: /vmb, /vmg (Metoda reprezentacji)
ms.date: 11/04/2016
f1_keywords:
- /vmb
- /vmg
helpviewer_keywords:
- vmb compiler option [C++]
- -vmg compiler option [C++]
- vmg compiler option [C++]
- -vmb compiler option [C++]
- /vmb compiler option [C++]
- representation method compiler options [C++]
- /vmg compiler option [C++]
ms.assetid: ecdb391c-7dab-40b1-916b-673d10889fd4
ms.openlocfilehash: 19d183ef8d1dd152043d7249d907c9d5b48de230
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254288"
---
# <a name="vmb-vmg-representation-method"></a>/vmb, /vmg (Metoda reprezentacji)

Wybierz metodę używaną przez kompilator do reprezentowania wskaźników do elementów członkowskich klasy.

Użyj **/VMB** , jeśli zawsze definiujesz klasę przed zadeklarowaniem wskaźnika do składowej klasy.

Użyj **/VMG** , aby zadeklarować wskaźnik do składowej klasy przed zdefiniowaniem klasy. Taka potrzeba może wystąpić w przypadku zdefiniowania elementów członkowskich w dwóch różnych klasach, które odwołują się do siebie nawzajem. Dla takich wzajemnie odwołujących się klas, przed zdefiniowaniem należy odwołać się do jednej klasy.

## <a name="syntax"></a>Składnia

```
/vmb
/vmg
```

## <a name="remarks"></a>Uwagi

Możesz również użyć [słowa kluczowego](../../cpp/inheritance-keywords.md) [pointers_to_members](../../preprocessor/pointers-to-members.md) lub dziedziczenia w kodzie, aby określić reprezentację wskaźnika.

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

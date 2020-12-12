---
description: Dowiedz się więcej na temat:/VMM,/VMS,/VMV (reprezentacja Ogólnego przeznaczenia)
title: /VMM,-VM,-VMV (reprezentacja Ogólnego przeznaczenia)
ms.date: 11/04/2016
f1_keywords:
- /vms
- /vmm
- /vmv
helpviewer_keywords:
- Virtual Inheritance compiler option
- general purpose representation compiler options
- vms compiler option [C++]
- vmm compiler option [C++]
- /vmm compiler option [C++]
- -vmm compiler option [C++]
- -vms compiler option [C++]
- /vms compiler option [C++]
- vmv compiler option [C++]
- /vmv compiler option [C++]
- Single Inheritance compiler option
- -vmv compiler option [C++]
ms.assetid: 0fcd7ae0-3031-4c62-a2a8-e154c8685dae
ms.openlocfilehash: 8c5761a2f51ec9860a4afeb7d4aacbf7f882b3f1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257228"
---
# <a name="vmm-vms-vmv-general-purpose-representation"></a>/vmm, /vms, /vmv (Ogólna reprezentacja celu)

Używany, gdy jako [Metoda reprezentacji](vmb-vmg-representation-method.md)została wybrana wartość [/VMB,/VMG (Metoda reprezentacji)](vmb-vmg-representation-method.md) . Te opcje wskazują model dziedziczenia definicji klasy, która nie została jeszcze osiągnięta.

## <a name="syntax"></a>Składnia

```
/vmm
/vms
/vmv
```

## <a name="remarks"></a>Uwagi

Opcje są opisane w poniższej tabeli.

|Opcja|Opis|
|------------|-----------------|
|**/VMM**|Określa najbardziej ogólną reprezentację wskaźnika do składowej klasy, która korzysta z wielokrotnego dziedziczenia.<br /><br /> Odpowiednie [słowo kluczowe dziedziczenia](../../cpp/inheritance-keywords.md) i argument do [#pragma pointers_to_members](../../preprocessor/pointers-to-members.md) są **multiple_inheritance**.<br /><br /> Ta reprezentacja jest większa niż wymagana dla pojedynczego dziedziczenia.<br /><br /> Jeśli model dziedziczenia definicji klasy, do której jest zadeklarowany wskaźnik do składowej, jest wirtualny, kompilator generuje błąd.|
|**/VMS**|Określa najbardziej ogólną reprezentację wskaźnika do składowej klasy, która korzysta z braku dziedziczenia lub pojedynczego dziedziczenia.<br /><br /> Odpowiednie [słowo kluczowe dziedziczenia](../../cpp/inheritance-keywords.md) i argument do [#pragma pointers_to_members](../../preprocessor/pointers-to-members.md) są **single_inheritance**.<br /><br /> Jest to najmniejsza możliwa reprezentacja wskaźnika do składowej klasy.<br /><br /> Jeśli model dziedziczenia definicji klasy, do której jest zadeklarowany wskaźnik do składowej, jest wielokrotne lub wirtualne, kompilator generuje błąd.|
|**/VMV**|Określa najbardziej ogólną reprezentację wskaźnika do składowej klasy, która korzysta z wirtualnego dziedziczenia. Nigdy nie powoduje błędu i jest wartością domyślną.<br /><br /> Odpowiednie [słowo kluczowe dziedziczenia](../../cpp/inheritance-keywords.md) i argument do [#pragma pointers_to_members](../../preprocessor/pointers-to-members.md) są **virtual_inheritance**.<br /><br /> Ta opcja wymaga większego wskaźnika i dodatkowego kodu do interpretacji wskaźnika niż inne opcje.|

Po określeniu jednej z tych opcji modelu dziedziczenia ten model jest używany dla wszystkich wskaźników do elementów członkowskich klasy, niezależnie od ich typu dziedziczenia lub od tego, czy wskaźnik jest zadeklarowany przed lub po klasie. W związku z tym, jeśli zawsze używasz klas jednodziedziczenia, możesz zmniejszyć rozmiar kodu, kompilując z **/VMS**; Jeśli jednak chcesz użyć najbardziej ogólnego przypadku (kosztem największego przedstawienia danych), skompiluj z **/VMV**.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **C/C++** .

1. Kliknij stronę właściwości **wiersza polecenia** .

1. Wpisz opcję kompilatora w polu **dodatkowe opcje** .

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Zobacz też

[/VMB,/VMG (Metoda reprezentacji)](vmb-vmg-representation-method.md)<br/>
[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)

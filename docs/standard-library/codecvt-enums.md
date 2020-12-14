---
description: 'Dowiedz się więcej na temat: &lt; &gt; wyliczenia codecvt'
title: '&lt;&gt;wyliczenia codecvt'
ms.date: 11/04/2016
f1_keywords:
- codecvt/std::codecvt_mode
ms.assetid: 46a8b073-01bc-46d3-b3d3-a8540f9422c1
helpviewer_keywords:
- std::codecvt_mode
ms.openlocfilehash: bcd40f72f563b3ecf91125f7167f206d4b1b6517
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234062"
---
# <a name="ltcodecvtgt-enums"></a>&lt;&gt;wyliczenia codecvt

## <a name="codecvt_mode-enumeration"></a><a name="codecvt_mode"></a> codecvt_mode, Wyliczenie

Określa informacje o konfiguracji dla zestawów reguł [ustawień regionalnych](../standard-library/locale-class.md) .

```cpp
enum codecvt_mode {
    consume_header = 4,
    generate_header = 2,
    little_endian = 1
};
```

### <a name="remarks"></a>Uwagi

Wyliczenie definiuje trzy stałe, które dostarczają informacje o konfiguracji do zestawów reguł ustawień regionalnych zadeklarowanych w [\<codecvt>](../standard-library/codecvt.md) . Unikatowe wartości to:

- `consume_header`, aby użyć początkowej sekwencji nagłówka podczas odczytywania sekwencji wielobajtowej i ustalania przyciągania dla kolejnej sekwencji wielobajtowej do odczytu

- `generate_header`, aby wygenerować początkową sekwencję nagłówka podczas pisania sekwencji wielobajtowej w celu anonsowania liczby bajtów kolejnej sekwencji wielobajtowej do zapisania

- `little_endian`, aby wygenerować sekwencję wielobajtową w kolejności little-endian, w przeciwieństwie do domyślnej kolejności big-endian

Te stałe mogą być logicznie razem w dowolnej kombinacji.

## <a name="see-also"></a>Zobacz też

[\<codecvt>](../standard-library/codecvt.md)

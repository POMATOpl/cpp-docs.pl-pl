---
description: 'Dowiedz się więcej o: vtordisp pragma'
title: vtordisp, pragma
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.vtordisp
- vtordisp_CPP
helpviewer_keywords:
- pragmas, vtordisp
- vtordisp pragma
ms.assetid: 05b7d73c-43fa-4b62-8c8a-170a9e427391
ms.openlocfilehash: 2cbb8b09584224a454dfe23d5dfd4500f09a1d9b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149646"
---
# <a name="vtordisp-pragma"></a>vtordisp, pragma

**Specyficzne dla języka C++**

Kontroluje dodanie ukrytego `vtordisp` elementu członkowskiego przemieszczenia konstrukcji/niszczenia.

## <a name="syntax"></a>Składnia

> **#pragma vtordisp (** [ **push,** ] *n* **)**\
> **#pragma vtordisp (pop)**\
> **#pragma vtordisp ()**\
> **#pragma vtordisp (** [ **push,** ] { **on**  |  **off** } **)**

### <a name="parameters"></a>Parametry

**wydajności**\
Wypchnięcie bieżące `vtordisp` ustawienie na wewnętrznym stosie kompilatora i ustawia nowe `vtordisp` ustawienie na *n*.  Jeśli *n* nie jest określony, bieżące `vtordisp` ustawienie nie zmieni się.

**skakując**\
Usuwa górny rekord z wewnętrznego stosu kompilatora i przywraca `vtordisp` ustawienie do usuniętej wartości.

*Azotan*\
Określa nową wartość `vtordisp` Ustawienia. Możliwe wartości to 0, 1 lub 2, odpowiadające `/vd0` `/vd1` opcjom, i `/vd2` kompilatora. Aby uzyskać więcej informacji, zobacz [/VD (Wyłącz przemieszczanie konstrukcji)](../build/reference/vd-disable-construction-displacements.md).

**z**\
Odpowiednik `#pragma vtordisp(1)` .

**Logowanie**\
Odpowiednik `#pragma vtordisp(0)` .

## <a name="remarks"></a>Uwagi

Pragma **vtordisp** jest stosowana tylko do kodu, który używa wirtualnych baz. Jeśli w klasie pochodnej przeciążono funkcję wirtualną, która jest dziedziczona z wirtualnej klasy bazowej, oraz jeśli konstruktor lub destruktor klasy pochodnej wywoła tę funkcję za pomocą wskaźnika do wirtualnej klasy bazowej, kompilator może wprowadzić dodatkowe ukryte pola `vtordisp` do klas z bazami wirtualnymi.

Pragma **vtordisp** ma wpływ na układ klas, które go obserwują. `/vd0`Opcje, `/vd1` i `/vd2` określają takie samo zachowanie dla kompletnych modułów. Określenie wartości 0 lub **wyłączenie** powoduje pominięcie ukrytych `vtordisp` elementów członkowskich. Wyłącz **vtordisp** tylko wtedy, gdy nie ma możliwości, że konstruktory i destruktory klasy wywołują funkcje wirtualne na obiekcie wskazywanym przez **`this`** wskaźnik.

W przypadku wybrania opcji 1 lub **na** wartość domyślna włączane `vtordisp` są ukryte elementy członkowskie, w których są one potrzebne.

Określenie 2 włącza ukryte `vtordisp` elementy członkowskie dla wszystkich wirtualnych baz z funkcjami wirtualnymi.  `#pragma vtordisp(2)` może być konieczne w celu zapewnienia prawidłowej wydajności **`dynamic_cast`** dla częściowo skonstruowanego obiektu. Aby uzyskać więcej informacji, zobacz [Ostrzeżenie kompilatora (poziom 1) C4436](../error-messages/compiler-warnings/compiler-warning-level-1-c4436.md).

`#pragma vtordisp()`, bez argumentów, przywraca `vtordisp` ustawienie początkowe ustawienie.

```cpp
#pragma vtordisp(push, 2)
class GetReal : virtual public VBase { ... };
#pragma vtordisp(pop)
```

**ZAKOŃCZENIE specyficzne dla języka C++**

## <a name="see-also"></a>Zobacz też

[Dyrektywy pragma i słowo kluczowe __pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)

---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4462'
title: Ostrzeżenie kompilatora (poziom 1) C4462
ms.date: 10/25/2017
f1_keywords:
- C4462
helpviewer_keywords:
- C4462
ms.assetid: 4e20aca4-293e-4c75-a83d-961c27ab7840
ms.openlocfilehash: 81696df228b2cbe6278521f602d2a6f986cacb13
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212535"
---
# <a name="compiler-warning-level-1-c4462"></a>Ostrzeżenie kompilatora (poziom 1) C4462

> nie można określić GUID typu. Program może ulec awarii w czasie wykonywania.

Ostrzeżenie C4462 występuje w aplikacji lub składniku środowisko wykonawcze systemu Windows, gdy publiczny `TypedEventHandler` ma jeden z parametrów typu jako odwołanie do otaczającej klasy.

To ostrzeżenie jest automatycznie podwyższana do błędu. Jeśli chcesz zmodyfikować to zachowanie, użyj [#pragma ostrzeżenie](../../preprocessor/warning.md). Na przykład, aby C4462 na problem z ostrzeżeniem poziomu 4, Dodaj ten wiersz do pliku kodu źródłowego:

```cpp
#pragma warning(4:4462)
```

## <a name="example"></a>Przykład

Ten przykład generuje ostrzeżenie C4462:

```cpp
namespace N
{
    public ref struct EventArgs sealed {};
    public ref struct R sealed
    {
        R() {}
        event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e;
    };
}

[Platform::MTAThread]
int main()
{
    auto x = ref new N::R();
}
```

Istnieją dwa sposoby obejścia tego błędu. Jednym ze sposobów, pokazanym w następnym przykładzie, jest zapewnienie zdarzeniu wewnętrznej dostępności, tak aby było ono dostępne dla kodu w tym samym pliku wykonywalnym, ale nie dla kodu w innych składnikach systemu Windows czasu wykonywania.

```cpp
internal:
    event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e;
```

Jeśli zdarzenie musi być publiczne, można użyć innego obejścia, które polega na uwidocznieniu go przez interfejs domyślny:

```cpp
ref struct R;
public interface struct IR{ event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e;};

public ref struct R sealed : [Windows::Foundation::Metadata::Default] IR
{
    R() {}
    virtual event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e;
};
```

Identyfikator GUID typu `Windows::Foundation::TypedEventHandler<R^, EventArgs^>^` jest używany tylko podczas uzyskiwania dostępu do typu z innego składnika. Pierwsza metoda obejścia problemu jest skuteczna, ponieważ może on być dostępny wyłącznie w ramach własnego składnika po zastosowaniu obejścia. W przeciwnym razie kompilator musi założyć najgorszy przypadek i wygenerować ostrzeżenie.

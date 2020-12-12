---
description: Dowiedz się więcej na temat klasy enable_shared_from_this
title: enable_shared_from_this — Klasa
ms.date: 11/04/2016
f1_keywords:
- memory/std::enable_shared_from_this
helpviewer_keywords:
- enable_shared_from_this class
- enable_shared_from_this
ms.assetid: 9237603d-22e2-421f-b070-838ac006baf5
ms.openlocfilehash: 6c6103846810bee07000821f4613c8f7979174ae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97232671"
---
# <a name="enable_shared_from_this-class"></a>enable_shared_from_this — Klasa

Pomaga wygenerować `shared_ptr` .

## <a name="syntax"></a>Składnia

```cpp
class enable_shared_from_this {
public:
    shared_ptr<Ty>
        shared_from_this();
    shared_ptr<const Ty> shared_from_this() const;
    weak_ptr<T> weak_from_this() noexcept;
    weak_ptr<T const> weak_from_this() const noexcept;
protected:
    enable_shared_from_this();
    enable_shared_from_this(const enable_shared_from_this&);
    enable_shared_from_this& operator=(const enable_shared_from_this&);
    ~enable_shared_from_this();
};
```

### <a name="parameters"></a>Parametry

*Br*\
Typ kontrolowany przez wspólny wskaźnik.

## <a name="remarks"></a>Uwagi

Obiekty pochodzące z `enable_shared_from_this` mogą używać `shared_from_this` metod w funkcjach składowych do tworzenia [shared_ptr](../standard-library/shared-ptr-class.md) właścicieli wystąpienia, które współdzielą własność z istniejącymi `shared_ptr` właścicielami. W przeciwnym razie, jeśli tworzysz nowy `shared_ptr` przy użyciu **`this`** , jest on odrębny od istniejących `shared_ptr` właścicieli, co może prowadzić do nieprawidłowych odwołań lub spowodować, że obiekt zostanie usunięty więcej niż raz.

Konstruktory, destruktory i operator przypisania są chronione, aby zapobiec przypadkowemu nadużyciom. Typ argumentu *szablonu musi być typem klasy* pochodnej.

Przykład użycia można znaleźć w temacie [enable_shared_from_this:: shared_from_this](#shared_from_this).

## <a name="shared_from_this"></a><a name="shared_from_this"></a> shared_from_this

Generuje `shared_ptr` udział własności wystąpienia z istniejącymi `shared_ptr` właścicielami.

```cpp
shared_ptr<T> shared_from_this();
shared_ptr<const T> shared_from_this() const;
```

### <a name="remarks"></a>Uwagi

Podczas wyprowadzania obiektów z `enable_shared_from_this` klasy bazowej `shared_from_this` funkcje składowe szablonu zwracają [shared_ptr obiektu klasy](../standard-library/shared-ptr-class.md) , który współużytkuje własność tego wystąpienia z istniejącymi `shared_ptr` właścicielami. W przeciwnym razie, jeśli utworzysz nowy `shared_ptr` z **`this`** , jest on odrębny od istniejących `shared_ptr` właścicieli, co może prowadzić do nieprawidłowych odwołań lub spowodować usunięcie obiektu więcej niż raz. Zachowanie jest niezdefiniowane, jeśli wywołujesz `shared_from_this` wystąpienie, które nie jest już własnością `shared_ptr` obiektu.

### <a name="example"></a>Przykład

```cpp
// std_memory_shared_from_this.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

using namespace std;

struct base : public std::enable_shared_from_this<base>
{
    int val;
    shared_ptr<base> share_more()
    {
        return shared_from_this();
    }
};

int main()
{
    auto sp1 = make_shared<base>();
    auto sp2 = sp1->share_more();

    sp1->val = 3;
    cout << "sp2->val == " << sp2->val << endl;
    return 0;
}
```

```Output
sp2->val == 3
```

## <a name="weak_from_this"></a><a name="weak_from_this"></a> weak_from_this

```cpp
weak_ptr<T> weak_from_this() noexcept;
weak_ptr<T const> weak_from_this() const noexcept;
```

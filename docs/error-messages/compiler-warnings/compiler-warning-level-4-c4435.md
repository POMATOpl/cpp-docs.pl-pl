---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4435'
title: Ostrzeżenie kompilatora (poziom 4) C4435
ms.date: 11/04/2016
f1_keywords:
- C4435
helpviewer_keywords:
- C4435
ms.assetid: a04524af-2b71-4ff9-9729-d9d1d1904ed7
ms.openlocfilehash: ce5ee4e32f6efa1e7986d55fafa0ceec8b754351
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203513"
---
# <a name="compiler-warning-level-4-c4435"></a>Ostrzeżenie kompilatora (poziom 4) C4435

'klasa1': Układ obiektu pod /vd2 zmieni się ze względu na wirtualną klasę podstawową 'klasa2'

To ostrzeżenie jest domyślnie wyłączone. Aby uzyskać więcej informacji [, zobacz ostrzeżenia kompilatora, które są domyślnie wyłączone](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

W obszarze domyślna opcja kompilacji elementu/vd1 Klasa pochodna nie ma `vtordisp` pola dla wskazanej bazy wirtualnej.  Jeśli/VD2 zmieni lub `#pragma vtordisp(2)` jest w efekcie, `vtordisp` pole będzie obecne, zmieniając układ obiektu.  Może to prowadzić do problemów ze zgodnością binarną, jeśli korzystanie z modułów jest kompilowane z innymi `vtordisp` ustawieniami.

## <a name="example"></a>Przykład

Poniższy przykład generuje C4435.

```cpp
// C4435.cpp
// compile with: /c /W4
#pragma warning(default : 4435)
class A
{
public:
    virtual ~A() {}
};

class B : public virtual A  // C4435
{};
```

## <a name="see-also"></a>Zobacz też

[vtordisp](../../preprocessor/vtordisp.md)<br/>
[/VD (Wyłącz przemieszczanie konstrukcji)](../../build/reference/vd-disable-construction-displacements.md)

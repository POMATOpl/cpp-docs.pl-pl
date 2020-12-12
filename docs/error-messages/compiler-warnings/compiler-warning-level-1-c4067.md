---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4067'
title: Ostrzeżenie kompilatora (poziom 1) C4067
ms.date: 11/04/2016
f1_keywords:
- C4067
helpviewer_keywords:
- C4067
ms.assetid: 1d10353e-8cd5-4b01-9184-a06189b965a4
ms.openlocfilehash: b11167ba5648e71be16197ecfb418d92cb5d879a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267667"
---
# <a name="compiler-warning-level-1-c4067"></a>Ostrzeżenie kompilatora (poziom 1) C4067

> nieoczekiwane tokeny po dyrektywie preprocesora-oczekiwano nowego wiersza

## <a name="remarks"></a>Uwagi

Kompilator odnalazł i zignorował dodatkowe znaki po dyrektywie preprocesora. Może to być spowodowane wszelkimi nieoczekiwanymi znakami, chociaż częstą przyczyną jest bezproblemowy średnik po dyrektywie. Komentarze nie powodują tego ostrzeżenia. Opcja kompilatora **/za** włącza to ostrzeżenie dla większej liczby dyrektyw preprocesora niż ustawienie domyślne.

## <a name="example"></a>Przykład

```cpp
// C4067a.cpp
// compile with: cl /EHsc /DX /W1 /Za C4067a.cpp
#include <iostream>
#include <string> s     // C4067
#if defined(X);         // C4067
std::string s{"X is defined"};
#else
std::string s{"X is not defined"};
#endif;                 // C4067 only under /Za
int main()
{
    std::cout << s << std::endl;
}
```

Aby usunąć to ostrzeżenie, Usuń niewidoczne znaki lub przenieś je do bloku komentarz. Niektóre ostrzeżenia C4067 można wyłączyć, usuwając opcję kompilatora **/za** .

```cpp
// C4067b.cpp
// compile with: cl /EHsc /DX /W1 C4067b.cpp
#include <iostream>
#include <string>
#if defined(X)
std::string s{"X is defined"};
#else
std::string s{"X is not defined"};
#endif
int main()
{
    std::cout << s << std::endl;
}
```

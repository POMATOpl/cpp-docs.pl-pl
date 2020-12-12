---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4910'
title: Ostrzeżenie kompilatora (poziom 1) C4910
ms.date: 11/04/2016
f1_keywords:
- C4910
helpviewer_keywords:
- C4910
ms.assetid: 67963560-fbca-4ca7-93db-06beaf7055f0
ms.openlocfilehash: 4798ba8ae8005239c9cf83e109bdb0f9e4c01928
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291457"
---
# <a name="compiler-warning-level-1-c4910"></a>Ostrzeżenie kompilatora (poziom 1) C4910

" \<identifier> ": "__declspec (dllexport)" i "extern" są niezgodne z jawnym wystąpieniem

Jawne wystąpienie szablonu o nazwie *\<identifier>* jest modyfikowane przez `__declspec(dllexport)` **`extern`** słowa kluczowe i. Jednak te słowa kluczowe wykluczają się wzajemnie. `__declspec(dllexport)`Słowo kluczowe oznacza wystąpienie klasy szablonu, natomiast **`extern`** słowo kluczowe oznacza, że nie tworzy automatycznie wystąpienia klasy szablonu.

## <a name="see-also"></a>Zobacz też

[Jawne utworzenie wystąpienia](../../cpp/explicit-instantiation.md)<br/>
[dllexport, dllimport](../../cpp/dllexport-dllimport.md)<br/>
[Ogólne zasady i ograniczenia](../../cpp/general-rules-and-limitations.md)

---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1383'
title: Błąd krytyczny C1383
ms.date: 11/04/2016
f1_keywords:
- C1383
helpviewer_keywords:
- C1383
ms.assetid: ca224d14-d687-4fd6-80c2-8b82f28924ea
ms.openlocfilehash: df20ac07cb3a6c94ff04b42b48ce23f168bb78c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276507"
---
# <a name="fatal-error-c1383"></a>Błąd krytyczny C1383

Opcja kompilatora/GL jest niezgodna z zainstalowaną wersją środowiska uruchomieniowego języka wspólnego

C1383 występuje w przypadku używania poprzedniej wersji środowiska uruchomieniowego języka wspólnego z nowszym kompilatorem i podczas kompilowania z **/CLR** i **/GL.**

Aby rozwiązać ten problem, należy użyć opcji **/GL** with **/CLR** lub zainstalować wersję środowiska uruchomieniowego języka wspólnego, która została dostarczona z kompilatorem.

Aby uzyskać więcej informacji, zobacz [/CLR (Kompilacja środowiska uruchomieniowego języka wspólnego)](../../build/reference/clr-common-language-runtime-compilation.md) i [/GL (Optymalizacja całego programu)](../../build/reference/gl-whole-program-optimization.md).

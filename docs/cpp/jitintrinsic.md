---
description: 'Dowiedz się więcej na temat: jitintrinsic'
title: jitintrinsic
ms.date: 11/04/2016
f1_keywords:
- jitintrinsic
- jitintrinsic_cpp
helpviewer_keywords:
- __declspec keyword [C++], jitintrinsic
- jitintrinsic __declspec modifier
ms.assetid: 23dbe416-7ef6-442b-b16d-9a81aab04fa6
ms.openlocfilehash: 29f4db3e946d2ccf0ec96bb0248e751bb9297db5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97292003"
---
# <a name="jitintrinsic"></a>jitintrinsic

Oznacza funkcję jako istotną dla 64-bitowego środowiska uruchomieniowego języka wspólnego. Jest on używany w przypadku niektórych funkcji w bibliotekach dostarczonych przez firmę Microsoft.

## <a name="syntax"></a>Składnia

```
__declspec(jitintrinsic)
```

## <a name="remarks"></a>Uwagi

**`jitintrinsic`** dodaje MODOPT ( <xref:System.Runtime.CompilerServices.IsJitIntrinsic> ) do sygnatury funkcji.

Użytkownicy nie odradzają korzystania z tego **`__declspec`** modyfikatora, ponieważ mogą wystąpić nieoczekiwane wyniki.

## <a name="see-also"></a>Zobacz też

[__declspec](../cpp/declspec.md)<br/>
[Słowa kluczowe](../cpp/keywords-cpp.md)

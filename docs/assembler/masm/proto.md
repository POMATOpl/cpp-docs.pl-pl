---
description: 'Dowiedz się więcej na temat: PROTO'
title: PROTO
ms.date: 12/06/2019
f1_keywords:
- PROTO
helpviewer_keywords:
- PROTO directive
ms.assetid: 0487ee16-9dc7-43d1-9445-cd1601f5a080
ms.openlocfilehash: 34dbf9d877dbbc52484e45c5f94212108aeacb42
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97126012"
---
# <a name="proto"></a>PROTO

Prototypuje funkcję lub procedurę. Można wywołać funkcję prototypową przez dyrektywę PROTO za pomocą dyrektywy [Invoke](invoke.md) .

## <a name="syntax"></a>Składnia

> *Label* **proto** ⟦*Distance*⟧ ⟦*Language-Type*⟧ ⟦__,__ ⟦*Parameter*⟧__:__*tag* ... ⟧

### <a name="parameters"></a>Parametry

*oznakowan*\
Nazwa funkcji prototypowej.

*odległość* (32-bitowa MASM). \
Obowiązkowe Używane w 16-bitowych modelach pamięci do przesłonięcia domyślnego i wskazuje **niemal** lub **daleko** wywołań.

*Typ języka* (tylko 32-bitowy MASM). \
Obowiązkowe Ustawia konwencję wywoływania i nazewnictwa dla procedur i symboli publicznych. Obsługiwane konwencje to:

- 32-bitowy model **płaski** : **C**, **stdcall**

- modele 16-bitowe: **C**, **Basic**, **Pascal**, **Pascal**, **syscall**, **stdcall**

*konstruktora*\
Opcjonalna nazwa parametru funkcji.

*seryjn*\
Typ parametru funkcji.

Parametry *parametrów* i *tagów* mogą pojawiać się wiele razy, raz dla każdego przerzuconego argumentu.

## <a name="example"></a>Przykład

Ten przykład pokazuje deklarację **proto** dla funkcji o nazwie `addup3` , która używa **blisko** wywołania do przesłania domyślnego modelu 16-bitowego dla wywołań procedur i używa konwencji wywoływania **C** dla parametrów stosu i zwracanych wartości. Przyjmuje dwa argumenty, **słowo** i **vararg**.

```MASM
addup3 PROTO NEAR C, argcount:WORD, arg1:VARARG
```

## <a name="see-also"></a>Zobacz też

[Dokumentacja dyrektyw](directives-reference.md)\
[. Odwołanie do modelu](dot-model.md)\
[MASM BNF, gramatyka](masm-bnf-grammar.md)

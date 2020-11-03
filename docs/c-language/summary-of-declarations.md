---
title: Podsumowanie deklaracji
description: Dowiedz się więcej na temat standardowej gramatyki C dla deklaracji zaimplementowanych przez kompilator Microsoft C/C++.
ms.date: 10/30/2020
ms.assetid: 53a5e9e5-1a33-40b5-9dea-7f669b479329
ms.openlocfilehash: 691424cc6f4efa59411397a13850d2057d4fcc50
ms.sourcegitcommit: 4abc6c4c9694f91685cfd77940987e29a51e3143
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2020
ms.locfileid: "93238463"
---
# <a name="summary-of-declarations"></a>Podsumowanie deklaracji

*`declaration`* :\
&emsp;*`declaration-specifiers`**`attribute-seq`* <sub>wybór</sub><sup>1</sup> *`init-declarator-list`* <sub>opt</sub>**`;`**\
&emsp;*`static_assert-declaration`*

*`declaration-specifiers`* :\
&emsp;*`storage-class-specifier`**`declaration-specifiers`* <sub>wybór</sub>\
&emsp;*`type-specifier`**`declaration-specifiers`* <sub>wybór</sub>\
&emsp;*`type-qualifier`**`declaration-specifiers`* <sub>wybór</sub>\
&emsp;*`function-specifier`**`declaration-specifiers`* <sub>wybór</sub>\
&emsp;*`alignment-specifier`**`declaration-specifiers`* <sub>wybór</sub>

*`attribute-seq`*<sup>1</sup>: \
&emsp;*`attribute`*<sup>1</sup> *`attribute-seq`* <sub>zgoda</sub><sup>1</sup>

*`attribute`*<sup>1, 2</sup>: jeden z \
&emsp;**`__asm`** **`__based`** **`__cdecl`** **`__clrcall`** **`__fastcall`** **`__inline`** **`__stdcall`** **`__thiscall`** **`__vectorcall`**

*`init-declarator-list`* :\
&emsp;*`init-declarator`*\
&emsp;*`init-declarator-list`* **`,`** *`init-declarator`*

*`init-declarator`* :\
&emsp;*`declarator`*\
&emsp;*`declarator`* **`=`** *`initializer`*

*`storage-class-specifier`* :\
&emsp;**`auto`**\
&emsp;**`extern`**\
&emsp;**`register`**\
&emsp;**`static`**\
&emsp;**`_Thread_local`**\
&emsp;**`typedef`**\
&emsp;**`__declspec`****`(`** *`extended-decl-modifier-seq`* **`)`** <sup>1</sup>

*`extended-decl-modifier-seq`*<sup>1</sup>: \
&emsp;*`extended-decl-modifier`*<sub>uszlachetniania</sub>\
&emsp;*`extended-decl-modifier-seq`* *`extended-decl-modifier`*

*`extended-decl-modifier`*<sup>1</sup>: \
&emsp;**`thread`**\
&emsp;**`naked`**\
&emsp;**`dllimport`**\
&emsp;**`dllexport`**

*`type-specifier`* :\
&emsp;**`void`**\
&emsp;**`char`**\
&emsp;**`short`**\
&emsp;**`int`**\
&emsp;**`__int8`**<sup>jedno</sup>\
&emsp;**`__int16`**<sup>jedno</sup>\
&emsp;**`__int32`**<sup>jedno</sup>\
&emsp;**`__int64`**<sup>jedno</sup>\
&emsp;**`long`**\
&emsp;**`float`**\
&emsp;**`double`**\
&emsp;**`signed`**\
&emsp;**`unsigned`**\
&emsp;**`_Bool`**\
&emsp;**`_Complex`**\
&emsp;*`atomic-type-specifier`*\
&emsp;*`struct-or-union-specifier`*\
&emsp;*`enum-specifier`*\
&emsp;*`typedef-name`*

*`struct-or-union-specifier`* :\
&emsp;*`struct-or-union`**`identifier`* <sub>opt</sub> **`{`** wybór *`struct-declaration-list`***`}`**\
&emsp;*`struct-or-union`* *`identifier`*

*`struct-or-union`* :\
&emsp;**`struct`**\
&emsp;**`union`**

*`struct-declaration-list`* :\
&emsp;*`struct-declaration`*\
&emsp;*`struct-declaration-list`* *`struct-declaration`*

*`struct-declaration`* :\
&emsp;*`specifier-qualifier-list`**`struct-declarator-list`* <sub>wybór</sub>**`;`**\
&emsp;*`static_assert-declaration`*

*`specifier-qualifier-list`* :\
&emsp;*`type-specifier`**`specifier-qualifier-list`* <sub>wybór</sub>\
&emsp;*`type-qualifier`**`specifier-qualifier-list`* <sub>wybór</sub>\
&emsp;*`alignment-specifier`**`specifier-qualifier-list`* <sub>wybór</sub>

*`struct-declarator-list`* :\
&emsp;*`struct-declarator`*\
&emsp;*`struct-declarator-list`* **`,`** *`struct-declarator`*

*`struct-declarator`* :\
&emsp;*`declarator`*\
&emsp;*`declarator`*<sub>wybór</sub> **`:`***`constant-expression`*

*`enum-specifier`* :\
&emsp;**`enum`***`identifier`* <sub>opt</sub> **`{`** wybór *`enumerator-list`***`}`**\
&emsp;**`enum`***`identifier`* <sub>opt</sub> **`{`** wybór *`enumerator-list`* **`,`****`}`**\
&emsp;**`enum`** *`identifier`*

*`enumerator-list`* :\
&emsp;*`enumerator`*\
&emsp;*`enumerator-list`* **`,`** *`enumerator`*

*`enumerator`* :\
&emsp;*`enumeration-constant`*\
&emsp;*`enumeration-constant`* **`=`** *`constant-expression`*

*`atomic-type-specifier`* :\
&emsp;**`_Atomic`** **`(`** *`type-name`* **`)`**

*`type-qualifier`* :\
&emsp;**`const`**\
&emsp;**`restrict`**\
&emsp;**`volatile`**\
&emsp;**`_Atomic`**

*`function-specifier`* :\
&emsp;**`inline`**\
&emsp;**`_Noreturn`**

*`alignment-specifier`* :\
&emsp;**`_Alignas`** **`(`** *`type-name`* **`)`**\
&emsp;**`_Alignas`** **`(`** *`constant-expression`* **`)`**

*`declarator`* :\
&emsp;*`pointer`*<sub>wybór</sub>*`direct-declarator`*

*`direct-declarator`* :\
&emsp;*`identifier`*\
&emsp;**`(`** *`declarator`* **`)`**\
&emsp;*`direct-declarator`***`[`** *`type-qualifier-list`* <sub>opt</sub> opt opt *`assignment-expression`* <sub>opt</sub>**`]`**\
&emsp;*`direct-declarator`***`[`** **`static`** *`type-qualifier-list`* <sub>wybór</sub> *`assignment-expression`***`]`**\
&emsp;*`direct-declarator`* **`[`** *`type-qualifier-list`* **`static`** *`assignment-expression`* **`]`**\
&emsp;*`direct-declarator`***`[`** *`type-qualifier-list`* <sub>opt</sub> wybór **`*`****`]`**\
&emsp;*`direct-declarator`* **`(`** *`parameter-type-list`* **`)`**\
&emsp;*`direct-declarator`***`(`** *`identifier-list`* <sub>wybór</sub> **`)`** <sup>3</sup>

*`pointer`* :\
&emsp;**`*`***`type-qualifier-list`* <sub>wybór</sub>\
&emsp;**`*`***`type-qualifier-list`* <sub>wybór</sub>*`pointer`*

*`type-qualifier-list`* :\
&emsp;*`type-qualifier`*\
&emsp;*`type-qualifier-list`* *`type-qualifier`*

*`parameter-type-list`* :\
&emsp;*`parameter-list`*\
&emsp;*`parameter-list`* **`,`** **`...`**

*`parameter-list`* :\
&emsp;*`parameter-declaration`*\
&emsp;*`parameter-list`* **`,`** *`parameter-declaration`*

*`parameter-declaration`* :\
&emsp;*`declaration-specifiers`* *`declarator`*\
&emsp;*`declaration-specifiers`**`abstract-declarator`* <sub>wybór</sub>

*`identifier-list`* :/ \* Dla deklarator starego stylu \*/\
&emsp;*`identifier`*\
&emsp;*`identifier-list`* **`,`** *`identifier`*

*`type-name`* :\
&emsp;*`specifier-qualifier-list`**`abstract-declarator`* <sub>wybór</sub>

*`abstract-declarator`* :\
&emsp;*`pointer`*\
&emsp;*`pointer`*<sub>wybór</sub>*`direct-abstract-declarator`*

*`direct-abstract-declarator`* :\
&emsp;**`(`** *`abstract-declarator`* **`)`**\
&emsp;*`direct-abstract-declarator`***`[`** *`type-qualifier-list`* <sub>opt</sub> opt opt *`assignment-expression`* <sub>opt</sub>**`]`**\
&emsp;*`direct-abstract-declarator`***`[`** **`static`** *`type-qualifier-list`* <sub>wybór</sub> *`assignment-expression`***`]`**\
&emsp;*`direct-abstract-declarator`* **`[`** *`type-qualifier-list`* **`static`** *`assignment-expression`* **`]`**\
&emsp;*`direct-abstract-declarator`***`[`** *`type-qualifier-list`* <sub>opt</sub> wybór **`*`****`]`**\
&emsp;*`direct-abstract-declarator`*<sub>wybór</sub> **`(`** *`parameter-type-list`* <sub>wybór</sub>**`)`**

*`typedef-name`* :\
&emsp;*`identifier`*

*`initializer`* :\
&emsp;*`assignment-expression`*\
&emsp;**`{`** *`initializer-list`* **`}`**\
&emsp;**`{`** *`initializer-list`* **`, }`**

*`initializer-list`* :\
&emsp;*`designation`*<sub>wybór</sub>*`initializer`*\
&emsp;*`initializer-list`***`,`** *`designation`* <sub>wybór</sub>*`initializer`*

*`designation`* :\
&emsp;*`designator-list`* **`=`**

*`designator-list`* :\
&emsp;*`designator`*\
&emsp;*`designator-list`* *`designator`*

*`designator`* :\
&emsp;**`[`** *`constant-expression`* **`]`**\
&emsp;**`.`** *`identifier`*

*`static_assert-declaration`* :\
&emsp;**`_Static_assert`** **`(`** *`constant-expression`* **`,`** *`string-literal`* **`)`** **`;`**

<sup>1</sup> ten element gramatyczny jest specyficzny dla firmy Microsoft. \
<sup>2</sup> Aby uzyskać więcej informacji o tych elementach, zobacz,,,,,,, [`__asm`](../assembler/inline/asm.md) [`__clrcall`](../cpp/clrcall.md) [`__stdcall`](../cpp/stdcall.md) [`__based`](../cpp/based-grammar.md) [`__fastcall`](../cpp/fastcall.md) [`__thiscall`](../cpp/thiscall.md) [`__cdecl`](../cpp/cdecl.md) [`__inline`](../cpp/inline-functions-cpp.md) i [`__vectorcall`](../cpp/vectorcall.md) .
<sup>3</sup> ten styl jest przestarzały.

## <a name="see-also"></a>Zobacz też

[Konwencje wywoływania](../cpp/calling-conventions.md)\
[Gramatyka struktury frazy](./phrase-structure-grammar.md)\
[Przestarzałe konwencje wywoływania](../cpp/obsolete-calling-conventions.md)

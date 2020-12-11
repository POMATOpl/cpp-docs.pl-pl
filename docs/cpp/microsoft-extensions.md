---
description: 'Dowiedz się więcej o programie: rozszerzenia Microsoft'
title: Rozszerzenia Microsoft
ms.date: 11/04/2016
helpviewer_keywords:
- Microsoft extensions to C/C++
ms.assetid: 68654516-24ef-4f33-aae2-175f86cc1979
ms.openlocfilehash: f3a6bfb7e85c3b219d1dda67e051f731ecf54fe6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97161641"
---
# <a name="microsoft-extensions"></a>Rozszerzenia Microsoft

*`asm-statement`*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`__asm`***`assembly-instruction`* **`;`** <sub>wybór</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`__asm {`***`assembly-instruction-list`* **`} ;`** <sub>wybór</sub>  

*`assembly-instruction-list`*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*`assembly-instruction`***`;`** <sub>wybór</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*`assembly-instruction`***`;`** *`assembly-instruction-list`* **`;`** <sub>wybór</sub>

*`ms-modifier-list`*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*`ms-modifier`**`ms-modifier-list`* <sub>wybór</sub>

*`ms-modifier`*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`__cdecl`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`__fastcall`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`__stdcall`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`__syscall`** (zarezerwowane dla przyszłych implementacji)<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`__oldcall`** (zarezerwowane dla przyszłych implementacji)<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`__unaligned`** (zarezerwowane dla przyszłych implementacji)<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*`based-modifier`*

*`based-modifier`*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`__based (`** *`based-type`* **`)`**

*`based-type`*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*`name`*

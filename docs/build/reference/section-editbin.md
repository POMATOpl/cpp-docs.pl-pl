---
description: Dowiedz się więcej na temat:/SECTION (polecenia EDITBIN)
title: /SECTION (EDITBIN)
ms.date: 11/04/2016
f1_keywords:
- /section_editbin
helpviewer_keywords:
- -SECTION editbin option
- SECTION editbin option
- alignment characters in sections
- /SECTION editbin option
ms.assetid: 4680ab4e-c984-4251-8241-93440cad7615
ms.openlocfilehash: 51d1305ca4f3e0e8222ae9408b44563a4c480d57
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224871"
---
# <a name="section-editbin"></a>/SECTION (EDITBIN)

```
/SECTION:name[=newname][,attributes][alignment]
```

## <a name="remarks"></a>Uwagi

Ta opcja zmienia atrybuty sekcji, zastępując atrybuty ustawione, gdy plik obiektu dla sekcji został skompilowany lub połączony.

Po dwukropku ( **:** ) Określ *nazwę* sekcji. Aby zmienić nazwę sekcji, należy użyć *nazwy* z znakiem równości (=) i *nowa_nazwa* dla sekcji.

Aby ustawić lub zmienić sekcję `attributes` , określ przecinek (**,**), po którym następuje jeden lub więcej atrybutów znaków. Aby Negate atrybut, poprzedź go znakiem wykrzyknika (!). Następujące znaki określają atrybuty pamięci:

|Atrybut|Ustawienie|
|---------------|-------------|
|c|kod|
|d|Odrzucanie|
|e|plik|
|mogę|zainicjowane dane|
|k|buforowana pamięć wirtualna|
|m|Usuwanie linku|
|o|Informacje o linku|
|p|stronicowana pamięć wirtualna|
|r|przeczytaj|
|s|udostępnione|
|u|Niezainicjowane dane|
|w|write (zapis)|

Aby kontrolować *wyrównanie*, określ znak **a** , po którym następuje jeden z następujących znaków, aby ustawić rozmiar wyrównania w bajtach w następujący sposób:

|Znak|Rozmiar wyrównania w bajtach|
|---------------|-----------------------------|
|1|1|
|2|2|
|4|4|
|8|8|
|p|16|
|t|32|
|s|64|
|x|bez wyrównania|

Określ `attributes` znaki i *wyrównania* jako ciąg bez odstępów. W znakach nie jest rozróżniana wielkość liter.

## <a name="see-also"></a>Zobacz też

[Opcje polecenia EDITBIN](editbin-options.md)

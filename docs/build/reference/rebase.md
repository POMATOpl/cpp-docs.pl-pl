---
description: Dowiedz się więcej na temat:/REBASE
title: /REBASE
ms.date: 11/04/2016
f1_keywords:
- /rebase
helpviewer_keywords:
- base addresses [C++]
- -REBASE editbin option
- REBASE editbin option
- DLLs [C++], linking
- executable files [C++], base address
- /REBASE editbin option [C++]
ms.assetid: 3f89d874-af5c-485b-974b-fd205f6e1a4b
ms.openlocfilehash: 6cbbf0a21bd9306167fb165b63c22e810518e161
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225339"
---
# <a name="rebase"></a>/REBASE

```
/REBASE[:modifiers]
```

## <a name="remarks"></a>Uwagi

Ta opcja określa adresy podstawowe dla określonych plików. POLECENIA EDITBIN przypisuje nowe adresy podstawowe w ciągłej przestrzeni adresowej, zgodnie z rozmiarem każdego pliku zaokrąglonego do najbliższej 64 KB. Aby uzyskać szczegółowe informacje na temat adresów bazowych, zobacz opcja konsolidatora [Address Base](base-base-address.md) (/Base).

Określ pliki wykonywalne i biblioteki DLL programu w argumencie *Files* w wierszu polecenia polecenia EDITBIN w kolejności, w jakiej mają być oparte. Opcjonalnie można określić jeden lub więcej *modyfikatorów*, każdy oddzielony przecinkami (**,**):

|Modyfikator|Akcja|
|--------------|------------|
|**Podstawa =**<em>adres</em>|Zapewnia adres początkowy do ponownego przypisania adresów bazowych do plików. Określ *adres* w notacji dziesiętnej lub w języku C. Jeśli baza nie jest określona, domyślny początkowy adres podstawowy to 0x400000. Jeśli jest używany, należy określić wartość BASE, a *adres* ustawia koniec zakresu adresów podstawowych.|
|**BASEFILE**|Tworzy plik o nazwie COFFBASE.TXT, który jest plikiem tekstowym w formacie oczekiwanym przez opcję/BASE LINKu.|
|**NOTUJ**|Informuje polecenia EDITBIN o ponownym przypisaniu adresów bazowych w dół od adresu końcowego. Pliki zostaną ponownie przypisane w podanej kolejności przy użyciu pierwszego pliku znajdującego się w najwyższym możliwym adresie poniżej końca zakresu adresów. Baza musi być używana z usługą w dół, aby zapewnić wystarczającą przestrzeń adresową dla plików. Aby określić przestrzeń adresową wymaganą przez określone pliki, należy uruchomić polecenia EDITBIN z/REBASE na plikach i dodać 64 KB do wyświetlanego łącznego rozmiaru.|

## <a name="see-also"></a>Zobacz też

[Opcje polecenia EDITBIN](editbin-options.md)

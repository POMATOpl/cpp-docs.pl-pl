---
description: Dowiedz się więcej na temat:/CLRHEADER
title: /CLRHEADER
ms.date: 05/16/2019
f1_keywords:
- /CLRHEADER
helpviewer_keywords:
- -CLRHEADER dumpbin option
- /CLRHEADER dumpbin option
- CLRHEADER dumpbin option
ms.assetid: cf73424f-4541-47e2-b94e-69b95266ef2a
ms.openlocfilehash: 8866707ae629672c3ae9ebb468d145eafb0475c4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182427"
---
# <a name="clrheader"></a>/CLRHEADER

Wyświetl informacje specyficzne dla środowiska CLR.

## <a name="syntax"></a>Składnia

> *Plik* /CLRHEADER

### <a name="arguments"></a>Argumenty

*rozszerzeniem*<br/>
Plik obrazu utworzony z [/CLR](clr-common-language-runtime-compilation.md).

## <a name="remarks"></a>Uwagi

**/CLRHEADER** wyświetla informacje o nagłówkach .NET używanych w dowolnym programie zarządzanym. Dane wyjściowe przedstawiają lokalizację i rozmiar w bajtach nagłówka i sekcji programu .NET w nagłówku.

Tylko opcja [/Headers](headers.md) polecenia DUMPBIN jest dostępna do użycia w przypadku plików utworzonych przy użyciu opcji kompilatora [/GL](gl-whole-program-optimization.md) .

Gdy **/CLRHEADER** jest używany w pliku, który został skompilowany z/CLR, w danych wyjściowych polecenia DUMPBIN będzie znajdował się **nagłówek CLR:** . Wartość **flag** wskazuje, która opcja/CLR została użyta:

- 0--/CLR (obraz może zawierać kod natywny).

Możesz również programowo sprawdzić, czy obraz został skompilowany dla środowiska uruchomieniowego języka wspólnego.  Aby uzyskać więcej informacji, zobacz [How to: Określanie, czy obraz jest natywny czy CLR](../../dotnet/how-to-determine-if-an-image-is-native-or-clr.md).

**/CLR: Pure** i **/CLR:** opcje kompilatora bezpiecznego są przestarzałe w programie Visual Studio 2015 i nie są obsługiwane w programie Visual Studio 2017 lub nowszym. Kod, który musi mieć wartość "Pure" lub "Safe", należy przenieść do języka C#.

## <a name="see-also"></a>Zobacz też

- [Opcje polecenia DUMPBIN](dumpbin-options.md)

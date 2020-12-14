---
description: 'Dowiedz się więcej o programie: korzystanie z CArchive &lt; &lt; i &gt; &gt; operatorów'
title: Korzystanie z CArchive &lt; &lt; i &gt; &gt; operatorów
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], loading from previously stored values
- CArchive class [MFC], storing and loading objects
- CArchive class [MFC], operators
ms.assetid: 56aef326-02dc-4992-8282-f0a4b78a064e
ms.openlocfilehash: a3e6d65ac2ff024f779edb6d23a43f7331628c3b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314571"
---
# <a name="using-the-carchive-ltlt-and-gtgt-operators"></a>Korzystanie z CArchive &lt; &lt; i &gt; &gt; operatorów

`CArchive` oferuje <\< and > operatory> do zapisywania i odczytywania prostych typów danych, a także `CObject` do i z pliku.

#### <a name="to-store-an-object-in-a-file-via-an-archive"></a>Aby zapisać obiekt w pliku za pośrednictwem archiwum

1. Poniższy przykład pokazuje, jak przechowywać obiekt w pliku za pośrednictwem archiwum:

   [!code-cpp[NVC_MFCSerialization#7](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_1.cpp)]

#### <a name="to-load-an-object-from-a-value-previously-stored-in-a-file"></a>Aby załadować obiekt z wartości wcześniej przechowywanej w pliku

1. Poniższy przykład pokazuje, jak załadować obiekt z wartości poprzednio przechowywanej w pliku:

   [!code-cpp[NVC_MFCSerialization#8](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_2.cpp)]

Zwykle przechowujesz i ładujesz dane do i z pliku za pośrednictwem archiwum w `Serialize` funkcjach `CObject` klas pochodnych, które muszą być zadeklarowane za pomocą makra DECLARE_SERIALIZE. Odwołanie do `CArchive` obiektu jest przesyłane do `Serialize` funkcji. Należy wywołać `IsLoading` funkcję `CArchive` obiektu, aby określić, czy `Serialize` funkcja została wywołana w celu załadowania danych z pliku lub zapisania danych do pliku.

`Serialize`Funkcja `CObject` klasy pochodnej do serializacji zazwyczaj ma następującą postać:

[!code-cpp[NVC_MFCSerialization#9](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_3.cpp)]

Powyższy szablon kodu jest dokładnie taki sam jak jeden AppWizard tworzony dla `Serialize` funkcji dokumentu (Klasa pochodna `CDocument` ). Ten szablon kodu ułatwia pisanie kodu, który jest łatwiejszy do przejrzenia, ponieważ kod przechowywania i kod ładowania powinny zawsze być równoległe, tak jak w poniższym przykładzie:

[!code-cpp[NVC_MFCSerialization#10](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_4.cpp)]

Biblioteka definiuje **`<<`** Operatory i **`>>`** dla nich `CArchive` jako pierwszy operand oraz następujące typy danych i typy klas jako drugi operand:

:::row:::
   :::column span="":::
      `BYTE`\
      `CObject*`\
      `COleCurrency`\
      `COleDateTime`\
      `COleDateTimeSpan`
   :::column-end:::
   :::column span="":::
      `COleVariant`\
      `CString`\
      `CTime` lub `CTimeSpan`\
      `Double`
   :::column-end:::
   :::column span="":::
      `DWORD`\
      `Float`\
      `Int`\
      `LONG`
   :::column-end:::
   :::column span="":::
      `POINT` lub `CPoint`\
      `RECT` lub `CRect`\
      `SIZE` lub `CSize`\
      `WORD`
   :::column-end:::
:::row-end:::

> [!NOTE]
> Przechowywanie i ładowanie `CObject` s za pośrednictwem archiwum wymaga dodatkowej uwagi. Aby uzyskać więcej informacji, zobacz artykuł [przechowywanie i ładowanie obiektów CObject za pomocą archiwum](../mfc/storing-and-loading-cobjects-via-an-archive.md).

`CArchive` **`<<`** Operatory i **`>>`** zawsze zwracają odwołanie do `CArchive` obiektu, który jest pierwszym operandem. Pozwala to na łańcuch operatorów, jak pokazano poniżej:

[!code-cpp[NVC_MFCSerialization#11](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_5.cpp)]

## <a name="see-also"></a>Zobacz też

[Serializacja: serializacja obiektu](../mfc/serialization-serializing-an-object.md)

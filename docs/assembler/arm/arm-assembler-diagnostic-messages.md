---
description: 'Dowiedz się więcej na temat: komunikaty diagnostyczne asemblera ARM'
title: Komunikaty diagnostyczne asemblera ARM
ms.date: 08/30/2018
f1_keywords:
- A2193
- A2196
- A2202
- A2513
- A2557
- A4228
- A4508
- A4509
helpviewer_keywords:
- A2193
- A2196
- A2202
- A2513
- A2557
- A4228
- A4508
- A4509
ms.assetid: 52b38267-6023-4bdc-a0ef-863362f48eec
ms.openlocfilehash: 91e4640c161cbb58522c3680ae5decdb4cc1e992
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118202"
---
# <a name="arm-assembler-diagnostic-messages"></a>Komunikaty diagnostyczne asemblera ARM

Asembler Microsoft ARM (*armasm*) emituje ostrzeżenia diagnostyczne i błędy podczas ich napotkania. W tym artykule opisano najczęściej spotykane komunikaty.

## <a name="syntax"></a>Składnia

> <em>filename</em>**(**<em>numer wiersza</em>**):** \[ **Ostrzeżenie o błędzie** | ] <em>numer</em>**:** *komunikat*

## <a name="diagnostic-messages---errors"></a>Komunikaty diagnostyczne — błędy

> A2193: Ta instrukcja generuje nieprzewidywalne zachowanie

Architektura ARM nie gwarantuje, co się dzieje, gdy ta instrukcja zostanie wykonana.  Aby uzyskać szczegółowe informacje o dobrze zdefiniowanych formularzach tej instrukcji, zapoznaj się z [instrukcją dotyczącą architektury ARM](https://go.microsoft.com/fwlink/p/?linkid=246464).

```asm
    ADD r0, r8, pc         ; A2193: this instruction generates unpredictable behavior
```

> A2196: nie można zakodować instrukcji w 16 bitach

Nie można zakodować określonej instrukcji jako 16-bitowej instrukcji kciuka.  Określ 32-bitową instrukcję lub Zmień rozmieszczenie kodu w celu przełączenia etykiety docelowej do zakresu instrukcji 16-bitowej.

Asembler może próbować zakodować gałąź w 16 bitach i zakończyć się niepowodzeniem z powodu tego błędu, nawet jeśli 32-bitowa rozgałęzienie jest encodable. Możesz rozwiązać ten problem, używając `.W` specyfikatora, aby jawnie oznaczyć gałąź jako 32-bitową.

```asm
    ADD.N r0, r1, r2      ; A2196: instruction cannot be encoded in 16 bits

    B.W label             ; OK
    B.N label             ; A2196: instruction cannot be encoded in 16 bits
    SPACE 10000
label
```

> A2202: składnia instrukcji pre-rejestrowania dostępu użytkowników nie jest dozwolona w regionie KCIUKa

Kod kciuka musi używać składni ujednoliconego języka asemblera (rejestrowania dostępu użytkowników).  Stara składnia nie jest już zaakceptowana

```asm
    ADDEQS r0, r1         ; A2202: Pre-UAL instruction syntax not allowed in THUMB region
    ADDSEQ r0, r1         ; OK
```

> A2513: obrót musi być parzysty

W trybie ARM istnieje alternatywna Składnia służąca do określania stałych.  Zamiast pisać, można `#<const>` napisać `#<byte>,#<rot>` , który reprezentuje wartość stałą, która jest uzyskiwana przez obrócenie wartości `<byte>` bezpośrednio przez `<rot>` .  W przypadku korzystania z tej składni należy wprowadzić wartość `<rot>` parzystą.

```asm
    MOV r0, #4, #2       ; OK
    MOV r0, #4, #1       ; A2513: Rotation must be even
```

> A2557: niepoprawna liczba bajtów do zapisu

Zgodnie z instrukcjami dotyczącymi ładowania i przechowywania struktury NEONu ( `VLDn` , `VSTn` ) istnieje alternatywna Składnia służąca do określania zapisu zwrotnego w rejestrze podstawowym.  Zamiast umieszczać wykrzyknika (!) po adresie, można określić natychmiastową wartość wskazującą przesunięcie, które ma zostać dodane do rejestru podstawowego.  W przypadku użycia tej składni należy określić dokładną liczbę bajtów, które zostały załadowane lub zapisane przez instrukcję.

```asm
    VLD1.8 {d0-d3}, [r0]!         ; OK
    VLD1.8 {d0-d3}, [r0], #32     ; OK
    VLD1.8 {d0-d3}, [r0], #100    ; A2557: Incorrect number of bytes to write back
```

## <a name="diagnostic-messages---warnings"></a>Komunikaty diagnostyczne — ostrzeżenia

> A4228: wartość wyrównania przekracza Wyrównanie obszaru; Wyrównanie nie jest gwarantowane

Wyrównanie określone w `ALIGN` dyrektywie jest większe niż wyrównanie otaczającej `AREA` .  W związku z tym asembler nie może zagwarantować, że dyrektywa zostanie wykorzystana `ALIGN` .

Aby rozwiązać ten problem, można określić w `AREA` dyrektywie `ALIGN` atrybut, który jest równy lub większy od żądanego wyrównania.

```asm
AREA |.myarea1|
ALIGN 8           ; A4228: Alignment value exceeds AREA alignment; alignment not guaranteed

AREA |.myarea2|,ALIGN=3
ALIGN 8           ; OK
```

> A4508: użycie tej obróconej stałej jest przestarzałe

W trybie ARM istnieje alternatywna Składnia służąca do określania stałych.  Zamiast pisać, można `#<const>` napisać `#<byte>,#<rot>` , który reprezentuje wartość stałą, która jest uzyskiwana przez obrócenie wartości `<byte>` bezpośrednio przez `<rot>` .  W niektórych kontekstach ARM nie korzystały z tych obróconych stałych. W takich przypadkach zamiast tego należy użyć `#<const>` składni podstawowej.

```asm
    ANDS r0, r0, #1                ; OK
    ANDS r0, r0, #4, #2            ; A4508: Use of this rotated constant is deprecated
```

> A4509: Ta forma instrukcji warunkowej jest przestarzała

Ta forma instrukcji warunkowej została zaniechana przez ARM w architekturze ARMv8. Zalecamy zmianę kodu w celu użycia gałęzi warunkowych. Aby sprawdzić, które instrukcje warunkowe są nadal obsługiwane, zapoznaj się z [instrukcją referencyjną dotyczącej architektury ARM](https://go.microsoft.com/fwlink/p/?linkid=246464).

To ostrzeżenie nie jest emitowane po użyciu przełącznika wiersza polecenia **-oldit** .

```asm
    ADDEQ r0, r1, r8              ; A4509: This form of conditional instruction is deprecated
```

## <a name="see-also"></a>Zobacz też

[Informacje Command-Line asemblera ARM](../../assembler/arm/arm-assembler-command-line-reference.md)<br/>
[Dyrektywy asemblera ARM](../../assembler/arm/arm-assembler-directives.md)<br/>

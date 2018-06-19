---
title: EDI ヘッダーをオーバーライドする |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 16c19d3d-eab2-4d44-8752-25aeadb537a4
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 510a3817d0fd99d43b6da9462c74dd8bc7c1bdf0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22265442"
---
# <a name="overriding-edi-headers"></a>EDI ヘッダーの上書き
EDI エンコード インターチェンジを送信する場合、メッセージに適用される EDI エンベロープは、通常、受信アグリーメントの EDI プロパティに、またはフォールバック アグリーメントのプロパティに基づきます。 しかし、多くの場合、ランタイムに生成される値に基づいて EDI エンベロープ プロパティを設定すると便利です。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、EdiOverride コンテキスト プロパティを使用して、送信ドキュメントで EDI エンベロープを生成するために使用する値を指定できます。  
  
## <a name="using-edioverride-context-properties"></a>EdiOverride コンテキスト プロパティの使用  
 EdiOverride コンテキスト プロパティを使用すると、EDI エンベロープを生成するために使用する値のすべてまたは一部を上書きできます。 EDI 送信パイプラインでは、エンベロープの作成に有効な値を格納する EdiOverride コンテキスト プロパティを使用します。 プロパティが設定されていない場合、パイプラインでは、アグリーメントのプロパティまたはフォールバック アグリーメントのプロパティ (アグリーメントが未定義の場合) で指定された値を使用します。 プロパティに無効な値が指定されている場合は、パイプラインではメッセージが中断し、検証エラーが報告されます。  
  
> [!NOTE]
>  EdiOverride コレクションで指定された値が使用されるのは、`EdiOverride.OverrideEdiHeader` プロパティがメッセージのコンテキストに書き込まれ、値 "True" が指定されている場合のみです。  
>   
>  既定では設定されません。  
  
### <a name="edioverride-properties-for-x12-envelope-values"></a>X12 エンベロープ値の EdiOverride プロパティ  
 次の表に、EdiOverride コンテキスト プロパティ、および対応する X12 エンベロープ ヘッダーを示します。  
  
|Header|[プロパティ]|  
|------------|----------------|  
|インターチェンジ制御ヘッダー (ISA)|ISA01、ISA02、ISA03、ISA04、ISA05、ISA06、ISA07、ISA08、ISA09、ISA10、ISA11、ISA12、ISA13、ISA14、ISA15、ISA16|  
|機能グループ ヘッダー (GS)|GS01、GS02、GS03、GS04、GS05、GS06、GS07、GS08|  
|トランザクション セット ヘッダー|ST02|  
  
### <a name="edioverride-properties-for-edifact-envelope-values"></a>EDIFACT エンベロープ値の EdiOverride プロパティ  
 次の表に、EdiOverride コンテキスト プロパティ、および対応する EDIFACT エンベロープ セグメントを示します。  
  
|Segment|[プロパティ]|  
|-------------|----------------|  
|文字列サービス通知 (UNA)|UNA1、UNA2、UNA3、UNA4、UNA5、UNA6、UNA6Suffix|  
|インターチェンジ制御ヘッダー (UNB)|UNB1_1、UNB1_2、UNB2_1、UNB2_2、UNB2_3、UNB3_1、UNB3_2、UNB3_3、UNB4_1、UNB4_2、UNB5、UNB6_1、UNB7、UNB8、UNB9、UNB10、UNB11|  
|機能グループ ヘッダー (UNG)|UNG1、UNG2_1、UNG2_2、UNG3_1、UNG3_2、UNG4_1、UNG4_2、UNG5、UNG6、UNG7_1、UNG7_2、UNG7_3、UNG8|  
|メッセージ ヘッダー (UNH)|UNH1|  
  
 判断するかどうかはこれらのヘッダーに関係なく、生成された、GenerateUNA プロパティと GenerateUNG プロパティを使用できます、UNA セグメントと UNG EDIFACT セグメントは省略可能なにあるため、 **UNA セグメントを適用**アグリーメント設定します。 次の表には、これらのセグメントの生成の結果の値を示します。  
  
|GenerateUNA コンテキスト プロパティ|[UNA セグメントを適用する] アグリーメント設定|エンジンの動作|  
|----------------------------------|-----------------------------------------|---------------------|  
|TRUE|CHECKED|UNA を生成する|  
|TRUE|UNCHECKED|UNA を生成する|  
|FALSE|CHECKED|UNA を生成しない|  
|FALSE|UNCHECKED|UNA を生成しない|  
|存在しない (OverrideEDIHeader が false)|CHECKED|UNA を生成する|  
|存在しない (OverrideEDIHeader が false)|UNCHECKED|UNA を生成しない|  
  
|GenerateUNG コンテキスト プロパティ|[UNG セグメントを適用する] アグリーメント設定|エンジンの動作|  
|----------------------------------|------------------------------------------|---------------------|  
|TRUE|CHECKED|UNG を生成する|  
|TRUE|UNCHECKED|UNG を生成する|  
|FALSE|CHECKED|UNG を生成しない|  
|FALSE|UNCHECKED|UNG を生成しない|  
|存在しない (OverrideEDIHeader が false)|CHECKED|UNG を生成する|  
|存在しない (OverrideEDIHeader が false)|UNCHECKED|UNG を生成しない|  
  
### <a name="group-envelopes"></a>グループ エンベロープ  
 インターチェンジには複数のグループが含まれる場合があるため、グループ エンベロープには特殊な課題があります。 この課題に対応するために、EDI 送信パイプラインは、インターチェンジ内のすべてのグループにエンベロープを適用することも、インターチェンジ内の唯一のグループにエンベロープを適用することもできます。  
  
 単一のトランザクションでは、すべての GS または UNG フィールドを上書きできます。バッチ インターチェンジの場合にのみ、次のフィールドを上書きできます。  
  
-   GS04  
  
-   GS05  
  
-   UNG4_1  
  
-   UNG4_2  
  
### <a name="batching"></a>バッチ処理  
 バッチ処理されたメッセージのトランザクション セット制御番号は、バッチ処理オーケストレーションで処理されます。 次のプロパティは、トランザクション セット制御番号の上書きをバッチ処理するために、任意のメッセージのコンテキストに書き込むことができます。  
  
-   ST02 (X12 メッセージの場合)  
  
-   UNH1 (EDIFACT メッセージの場合)  
  
> [!NOTE]
>  複数の受信メッセージに同じグループの同じ制御番号が含まれる場合、重複した番号のメッセージは中断されます。  
  
> [!NOTE]
>  バッチ処理するメッセージの EdiOverride コンテキスト プロパティ ISA、UNA、GS、UNG は昇格させないでください。 これらのプロパティを上書きする必要がある場合は、EDI 送信パイプラインに送信する前にバッチ オーケストレーションの出力メッセージで昇格してください。  
  
### <a name="delimiter-collision"></a>区切り記号の競合  
 UNA ヘッダーなどの区切り記号には、フィールドごとに一意な値が含まれている必要があります。 UNA ヘッダーなどの区切り記号の値を上書きする場合は、上書きする値内だけではなく、アグリーメントまたはフォールバック アグリーメント設定から使用するすべての区切り記号値間でも、各区切り記号値が一意である必要があります。  
  
 たとえば、UNA1、UNA2、UNA4 を上書きし、UNA3、UNA5、UNA6、UNA6Suffix がアグリーメントのプロパティから取得される場合、各プロパティには他と比較して一意な値が含まれている必要があります。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server が EDI メッセージを送信する方法](../core/how-biztalk-server-sends-edi-messages.md)
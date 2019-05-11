---
title: EDI ヘッダーの上書き |Microsoft Docs
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
ms.openlocfilehash: e768bb992497651a14558895e4bedf2dbff692fc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393369"
---
# <a name="overriding-edi-headers"></a>EDI ヘッダーのオーバーライド
EDI でエンコードされたインターチェンジを送信するときに、メッセージに適用される EDI エンベロープは通常、受信側アグリーメントの EDI のプロパティまたはフォールバック アグリーメントのプロパティに基づきます。 ただしの値を生成をランタイムに基づく EDI エンベロープのプロパティを設定すると便利です。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、EdiOverride コンテキスト プロパティを使用して、送信ドキュメントで EDI エンベロープの生成に使用される値を指定することができます。  
  
## <a name="using-edioverride-context-properties"></a>EdiOverride コンテキスト プロパティの使用  
 EdiOverride コンテキスト プロパティは、EDI エンベロープの生成に使用される値の一部またはすべてを上書きする方法を提供します。 EDI 送信パイプラインでは、エンベロープを構築する有効な値を格納する EdiOverride コンテキスト プロパティを使用します。 プロパティが設定されていない場合、アグリーメントが定義されていない場合、パイプラインはアグリーメントのプロパティまたはフォールバック アグリーメントのプロパティで指定された値を使用します。 プロパティに無効な値が含まれている場合、パイプラインがメッセージを中断し、検証エラーを報告します。  
  
> [!NOTE]
>  EdiOverride コレクションで指定された値は、場合にのみ使用されるが、`EdiOverride.OverrideEdiHeader`プロパティは、メッセージのコンテキストに書き込まれ、値"True"が含まれています。  
>   
>  既定値は設定されていません。  
  
### <a name="edioverride-properties-for-x12-envelope-values"></a>EdiOverride プロパティの X12 エンベロープ値  
 次の表は、EdiOverride コンテキスト プロパティと対応する X12 エンベロープ ヘッダー。  
  
|[ヘッダー]|プロパティ|  
|------------|----------------|  
|インターチェンジ制御ヘッダー (ISA)|ISA01、ISA02、ISA03、ISA04、ISA05、ISA06、ISA07、ISA08、ISA09、ISA10、ISA11、ISA12、ISA13、ISA14、ISA15、ISA16|  
|機能グループ ヘッダー (GS)|GS01、GS02、GS03、GS04、GS05、GS06、GS07、GS08|  
|トランザクション セット ヘッダー|ST02|  
  
### <a name="edioverride-properties-for-edifact-envelope-values"></a>EDIFACT エンベロープ値の EdiOverride プロパティ  
 次の表に、EdiOverride コンテキスト プロパティと対応する EDIFACT エンベロープ セグメントを示します。  
  
|Segment|プロパティ|  
|-------------|----------------|  
|文字列サービス通知 (UNA)|UNA1、UNA2、UNA3、UNA4、UNA5、UNA6、UNA6Suffix|  
|インターチェンジ制御ヘッダー (UNB)|UNB1_1、UNB1_2、UNB2_1、UNB2_2、UNB2_3、UNB3_1、UNB3_2、UNB3_3、UNB4_1、UNB4_2、UNB5、UNB6_1、UNB7、UNB8、UNB9、UNB10、UNB11|  
|機能グループ ヘッダー (UNG)|UNG1、UNG2_1、UNG2_2、UNG3_1、UNG3_2、UNG4_1、UNG4_2、UNG5、UNG6、UNG7_1、UNG7_2、UNG7_3、UNG8|  
|メッセージ ヘッダー (UNH)|UNH1|  
  
 関係なく、生成されたこれらのヘッダーがかどうかを判断する、GenerateUNA プロパティと GenerateUNG プロパティを使用できます、UNA セグメントと UNG EDIFACT セグメントは省略可能であるため、 **UNA セグメントを適用**アグリーメントの設定。 次の表は、これらのセグメントのジェネレーションで結果の値を示します。  
  
|GenerateUNA コンテキスト プロパティ|UNA セグメントのアグリーメント設定を適用します。|エンジンの動作|  
|----------------------------------|-----------------------------------------|---------------------|  
|TRUE|チェック|UNA を生成します。|  
|TRUE|オフ|UNA を生成します。|  
|FALSE|チェック|UNA を生成しません。|  
|FALSE|オフ|UNA を生成しません。|  
|存在しない (OverrideEDIHeader が false)|チェック|UNA を生成します。|  
|存在しない (OverrideEDIHeader が false)|オフ|UNA を生成しません。|  
  
|GenerateUNG コンテキスト プロパティ|UNG セグメントのアグリーメント設定を適用します。|エンジンの動作|  
|----------------------------------|------------------------------------------|---------------------|  
|TRUE|チェック|UNG を生成します。|  
|TRUE|オフ|UNG を生成します。|  
|FALSE|チェック|UNG を生成しません。|  
|FALSE|オフ|UNG を生成しません。|  
|存在しない (OverrideEDIHeader が false)|チェック|UNG を生成します。|  
|存在しない (OverrideEDIHeader が false)|オフ|UNG を生成しません。|  
  
### <a name="group-envelopes"></a>グループ エンベロープ  
 グループ エンベロープは、インターチェンジが存在する 1 つ以上のグループを持つことができますはの特殊な課題を提示します。 これに対処、EDI 送信パイプライン、インターチェンジ内のすべてのグループにエンベロープを適用するか、インターチェンジ内の唯一のグループにエンベロープを適用します。  
  
 1 つのトランザクションのすべての GS または UNG フィールドを上書きできます。 バッチ インターチェンジの場合、次のフィールドのみをオーバーライドすることができます。  
  
-   GS04  
  
-   GS05  
  
-   UNG4_1  
  
-   UNG4_2  
  
### <a name="batching"></a>バッチ処理  
 バッチ処理されたメッセージのトランザクション セット制御番号をオーバーライドすると、バッチ処理オーケストレーションによって処理されます。 次のプロパティは、トランザクション セット制御番号が上書きするバッチ処理されるメッセージのコンテキストを記述できます。  
  
-   ST02 (x12 メッセージ)  
  
-   UNH1 (EDIFACT メッセージの場合  
  
> [!NOTE]
>  複数の受信メッセージに同じグループ内の同じ制御番号が含まれている場合は、重複した番号を持つメッセージが中断されます。  
  
> [!NOTE]
>  バッチ処理するメッセージの EdiOverride のコンテキスト プロパティ ISA、UNA、GS、または UNG は昇格しないでください。 EDI を送信する前にバッチ オーケストレーションの出力メッセージで昇格してこれらのプロパティをオーバーライドする必要がある場合は、パイプラインに送信します。  
  
### <a name="delimiter-collision"></a>区切り記号の競合  
 UNA ヘッダーなどの区切り記号は、各フィールドに一意の値を含める必要があります。 UNA ヘッダーなどの区切り記号の値をオーバーライドする場合は、各区切り記号の値がオーバーライドするもアグリーメントまたはフォールバック アグリーメント設定から使用される任意の区切り記号値間の値だけでなく内で一意であることを確認する必要があります。  
  
 たとえば、UNA1、UNA2、UNA4 を上書きすると、UNA3、UNA5、UNA6、UNA6Suffix がアグリーメントのプロパティから取得、各プロパティは、他と比較して一意の値を含める必要があります。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server が EDI メッセージを送信する方法](../core/how-biztalk-server-sends-edi-messages.md)
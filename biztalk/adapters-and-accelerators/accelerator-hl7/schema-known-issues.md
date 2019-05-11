---
title: スキーマの既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- known issues, schemas
- schemas, known issues
ms.assetid: 17651462-baa9-448a-954c-c09e70640f17
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ba0257b3ac5898c639ef8fef1a7d93df19732e8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289734"
---
# <a name="schema-known-issues"></a>スキーマの既知の問題
このセクションには、スキーマ エラーを回避するために役立つ有用な情報が含まれています。  
  
## <a name="mcf21glodefxsd-schema"></a>MCF_21_GLO_DEF.xsd スキーマ  
 Templates\schemas\2.1 フォルダーにスキーマ MCF_21_GLO_DEF.xsd は Common231 プロジェクトの一部ではありません。  
  
## <a name="miscellaneous-errors-can-result-from-undeployed-schemas"></a>その他のエラーは、展開解除されたスキーマを被る可能性  
 解析またはシリアル化でエラーが識別されない場合は、プロパティ スキーマおよび一般的なスキーマ (MSH/確認) がデプロイされたことを確認します。 展開解除されたプロパティ スキーマおよび一般的なスキーマでは、その他のエラーが発生します。  
  
## <a name="if-the-starter-project-is-installed-but-the-hl7-2x-schemas-are-not-installed-running-the-schema-wizard-generates-an-error"></a>HL7、スタート プロジェクトにがインストールされている場合 2.X スキーマがインストールされていない、スキーマ ウィザードを実行するには、エラーが生成されます。  
 HL7 の Microsoft BizTalk Accelerator のカスタム インストールを実行するかどうか ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) でインストールする、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]しないインストール、HL7 2.X スキーマの操作を行いますが、スキーマ ウィザードを実行しようとスターター プロジェクト、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]が生成されます、エラーがあります。 この問題を解決では、インストール、HL7 2.X スキーマをもう一度、カスタム インストール プロセスを実行します。  
  
## <a name="msh91-enumeration-list-needs-to-be-updated"></a>MSH9.1 列挙リストを更新する必要があります。  
 によってインストールされている MSH_25_GLO_DEF スキーマ[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]セットアップ時にが含まれていない完全な列挙リストには MSH9.1 (MessageType) および MSH9.2 (EventTrigger)、HL72 記載されています。X 標準。 次の表は、メッセージの種類とトリガー イベントの値をメッセージ型を持つ値を格納するスキーマを使用する場合、関連付けられているテーブルに追加する必要があります。 たとえば、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]かは処理されません ^ Z99 メッセージ Table76 MSH_25_GLO_DEF での列挙型に「か」を追加して、か処理しないまで ^ Z99 メッセージ"Z99"MSH_25_GLO_DEF で Table3 の列挙型に追加するまで。  
  
 MSH9.1 または MSH9.2 のいずれかの列挙型に値を追加するには、メッセージ ヘッダーのスキーマには、列挙値を追加"するには」手順を参照して[列挙型の拡張](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)します。  
  
|フィールド/テーブル|列挙型に追加する値します。|  
|------------------|--------------------------------------|  
|MessageType/Table76|ARD、RDO、RRO|  
|TriggerEvent/Table3|K11、K13、K15、MFA、O22、Q11、Q13、Q15、Q26、Q27、Q28、Q29、R0R、Z73、Z74、Z75、Z76、Z77、Z78、Z79、Z80、Z81、Z82、Z83、Z84、Z85、Z86、Z87、Z88、Z89、Z90、Z91、Z92、Z93、Z94、Z95、Z96、Z97、Z98、Z99|  
|MessageStructure/Table354|ARD_A19、ORL_O22|  
  
## <a name="btahl7-does-not-support-schemas-with-an-ambiguous-structure"></a>BTAHL7 では、あいまいな構造を持つスキーマはサポートしません  
 BTAHL7 エンジンは、あいまいな構造を持つ HL7 スキーマに準拠しているメッセージ インスタンスを処理できません。 あいまいなスキーマの構造体には、HL7 標準で完全に定義されていない 1 つです。 このようなスキーマには、固定、OMD、ORD、および SUR. メッセージの種類  
  
## <a name="btahl7-will-return-a-segment-sequence-error-for-some-messages"></a>BTAHL7 には、いくつかのメッセージのセグメントのシーケンス エラーが返されます  
 BTAHL7 では、以下に示すスキーマに準拠したメッセージを処理できません。 これらのメッセージの本文の解析が失敗し、次のエラー。「セグメントのシーケンス エラーです (このセグメントの後に見つかったセグメントが無効です)。」 メッセージに影響を受けるセグメント Id は、以下に示します。 これらすべてのエラーの影響を受けるシーケンス番号は、「2」です。  
  
|バージョン|メッセージ型|トリガー イベント|セグメント ID|  
|-------------|------------------|-------------------|----------------|  
|V2.3|固定|C09|ORC_CommonOrderSegment|  
|V2.3|固定|C10|ORC_CommonOrderSegment|  
|V2.3|固定|C11|ORC_CommonOrderSegment|  
|V2.3|固定|C12|ORC_CommonOrderSegment|  
|V2.3|サー|P09|PSH_ProductSummaryHeader|  
|V2.3.1|固定|C09|ORC_CommonOrderSegment|  
|V2.3.1|固定|C10|ORC_CommonOrderSegment|  
|V2.3.1|固定|C11|ORC_CommonOrderSegment|  
|V2.3.1|固定|C12|ORC_CommonOrderSegment|  
|V2.3.1|サー|P09|PSH_ProductSummaryHeader<br />Segment|  
|V2.4|固定|C09|ORC_CommonOrder|  
|V2.4|固定|C10|ORC_CommonOrder|  
|V2.4|固定|C11|ORC_CommonOrder|  
|V2.4|固定|C12|ORC_CommonOrder|  
|V2.4|OMD|O03|ORC_CommonOrder|  
|V2.4|ORD|O04|ORC_CommonOrder|  
|V2.4|サー|P09|PSH_ProductSummaryHeader|  
|V2.5|固定|C09|ORC_CommonOrder|  
|V2.5|固定|C10|ORC_CommonOrder|  
|V2.5|固定|C11|ORC_CommonOrder|  
|V2.5|固定|C12|ORC_CommonOrder|  
|V2.5|OMD|O03|ORC_CommonOrder|  
|V2.5|ORD|O04|ORC_CommonOrder|  
|V2.5|サー|P09|PSH_ProductSummaryHeader"|  
|V2.5|RDE|025|PSH_ProductSummaryHeader"|  
|V2.5|OUL|リリース 24|PSH_ProductSummaryHeader"|  
|V2.5|OML|035|PSH_ProductSummaryHeader"|  
|V2.5|ORL|034|PSH_ProductSummaryHeader"|  
  
> [!NOTE]
>  バージョン 2.5 の上記のリストはすべてを網羅して「セグメント シーケンス エラー」が発生する追加のメッセージ型を含めることができます。  
  
## <a name="btahl7-does-not-support-some-v231-schemas"></a>BTAHL7 では、いくつか v2.3.1 スキーマはサポートしません  
 BTAHL7 セットアップ プログラムでは、v2.3.1 の次のスキーマはインストールされません。  
  
-   OMD_O01_231_GLO_DEF  
  
-   OMN_O01_231_GLO_DEF  
  
-   OMS_O01_231_GLO_DEF  
  
-   ORD_O02_231_GLO_DEF  
  
-   ORN_O02_231_GLO_DEF  
  
-   ORS_O02_231_GLO_DEF  
  
## <a name="see-also"></a>参照  
 [既知の問題](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)
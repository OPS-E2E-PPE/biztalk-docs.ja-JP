---
title: スキーマの既知の問題 |Microsoft ドキュメント
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
ms.openlocfilehash: 0568a892559ea119b9a198368b4521cbe49ddf45
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207962"
---
# <a name="schema-known-issues"></a>スキーマの既知の問題
このセクションには、スキーマ エラーを回避するために役立つ有用な情報が含まれています。  
  
## <a name="mcf21glodefxsd-schema"></a>MCF_21_GLO_DEF.xsd スキーマ  
 Templates\schemas\2.1 フォルダーには、スキーマ MCF_21_GLO_DEF.xsd と、Common231 プロジェクトの一部ではありません。  
  
## <a name="miscellaneous-errors-can-result-from-undeployed-schemas"></a>スキーマが展開されていないその他のエラーとなります  
 解析またはシリアル化でエラーを特定できない場合は、プロパティ スキーマおよび一般的なスキーマ (MSH/確認) を展開したことを確認します。 展開解除されるプロパティ スキーマおよび共通スキーマでは、その他のエラーが発生します。  
  
## <a name="if-the-starter-project-is-installed-but-the-hl7-2x-schemas-are-not-installed-running-the-schema-wizard-generates-an-error"></a>スタート プロジェクトがインストールされている場合、HL7 が 2.X スキーマがインストールされていない、スキーマ ウィザードを実行するには、エラーが生成されます。  
 カスタム インストールを実行する場合[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) にインストールする、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]スタート プロジェクトが、インストール、HL7 2.X スキーマのない場合、行いスキーマ ウィザードを実行しようとし、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]が生成されますエラーです。 この問題を解決では、インストール、HL7 2.X スキーマにもう一度、カスタム インストール プロセスを実行します。  
  
## <a name="msh91-enumeration-list-needs-to-be-updated"></a>MSH9.1 列挙リストを更新する必要があります。  
 によってインストールされている MSH_25_GLO_DEF スキーマ[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]セットアップ時に含まない完全な列挙リスト MSH9.1 (MessageType) および MSH9.2 (EventTrigger)、HL72 に含まれているとします。標準的な X です。 次の表では、メッセージの種類とトリガー イベントの値を値を含むメッセージ型のスキーマを使用する場合に、対応するテーブルを追加する必要が一覧表示します。 たとえば、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]かは処理されません ^ Z99 メッセージ Table76 MSH_25_GLO_DEF、内の列挙体に「か」を追加して、かは処理されませんまで ^ Z99 メッセージ MSH_25_GLO_DEF でテーブル 3 の列挙体に"Z99"を追加するまでです。  
  
 MSH9.1 または MSH9.2 のいずれかの列挙体に値を追加、メッセージ ヘッダーのスキーマには、列挙値を追加"するには」手順を参照してください。[列挙型の拡張](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)です。  
  
|フィールド/テーブル|列挙型に追加する値します。|  
|------------------|--------------------------------------|  
|MessageType/Table76|ARD、RDO、RRO|  
|TriggerEvent/テーブル 3|K11、K13、K15、MFA、O22、Q11、Q13、Q15、Q26、Q27、Q28、Q29、R0R、Z73、Z74、Z75、Z76、Z77、Z78、Z79、Z80、Z81、Z82、Z83、Z84、Z85、Z86、Z87、Z88、Z89、Z90、Z91、Z92、Z93、Z94、Z95、Z96、Z97、Z98、Z99|  
|MessageStructure/Table354|ARD_A19、ORL_O22|  
  
## <a name="btahl7-does-not-support-schemas-with-an-ambiguous-structure"></a>BTAHL7 があいまいな構造を持つスキーマをサポートしていません  
 BTAHL7 エンジンは、あいまいな構造を持つ HL7 スキーマに準拠しているメッセージ インスタンスを処理できません。 あいまいなスキーマ構造は、HL7 標準を完全に定義されていない 1 つです。 このようなスキーマには、その CSU、OMD、ORD、および SUR. メッセージ型が含まれます  
  
## <a name="btahl7-will-return-a-segment-sequence-error-for-some-messages"></a>BTAHL7 には、いくつかのメッセージのセグメントのシーケンス エラーが返されます  
 BTAHL7 では、以下に示すスキーマに準拠したメッセージを処理できません。 これらのメッセージの本文の解析は失敗し、次のエラーが発生しました:「セグメントのシーケンス エラーです (このセグメントの後に見つかったセグメントが無効です).」 メッセージに影響を受けるセグメント Id は次のとおりです。 これらすべてのエラーの影響を受けるシーケンス番号は、「2」です。  
  
|バージョン|メッセージの種類|トリガー イベント|セグメント ID|  
|-------------|------------------|-------------------|----------------|  
|V2.3|CSU|C09|ORC_CommonOrderSegment|  
|V2.3|CSU|C10|ORC_CommonOrderSegment|  
|V2.3|CSU|C11|ORC_CommonOrderSegment|  
|V2.3|CSU|C12|ORC_CommonOrderSegment|  
|V2.3|SUR|P09|PSH_ProductSummaryHeader|  
|V2.3.1|CSU|C09|ORC_CommonOrderSegment|  
|V2.3.1|CSU|C10|ORC_CommonOrderSegment|  
|V2.3.1|CSU|C11|ORC_CommonOrderSegment|  
|V2.3.1|CSU|C12|ORC_CommonOrderSegment|  
|V2.3.1|SUR|P09|PSH_ProductSummaryHeader<br />Segment|  
|V2.4|CSU|C09|ORC_CommonOrder|  
|V2.4|CSU|C10|ORC_CommonOrder|  
|V2.4|CSU|C11|ORC_CommonOrder|  
|V2.4|CSU|C12|ORC_CommonOrder|  
|V2.4|OMD|O03|ORC_CommonOrder|  
|V2.4|ORD|O04|ORC_CommonOrder|  
|V2.4|SUR|P09|PSH_ProductSummaryHeader|  
|V2.5|CSU|C09|ORC_CommonOrder|  
|V2.5|CSU|C10|ORC_CommonOrder|  
|V2.5|CSU|C11|ORC_CommonOrder|  
|V2.5|CSU|C12|ORC_CommonOrder|  
|V2.5|OMD|O03|ORC_CommonOrder|  
|V2.5|ORD|O04|ORC_CommonOrder|  
|V2.5|SUR|P09|PSH_ProductSummaryHeader"|  
|V2.5|RDE|025|PSH_ProductSummaryHeader"|  
|V2.5|OUL|リリース 24|PSH_ProductSummaryHeader"|  
|V2.5|OML|035|PSH_ProductSummaryHeader"|  
|V2.5|ORL|034|PSH_ProductSummaryHeader"|  
  
> [!NOTE]
>  2.5 のバージョンについては、上記のリストは完全ではないと、"セグメント シーケンスのエラーが発生します"その他のメッセージの種類を含めることができます。  
  
## <a name="btahl7-does-not-support-some-v231-schemas"></a>BTAHL7 が一部 v2.3.1 スキーマをサポートしていません  
 BTAHL7 セットアップ プログラムでは、次の v2.3.1 スキーマはインストールされません。  
  
-   OMD_O01_231_GLO_DEF  
  
-   OMN_O01_231_GLO_DEF  
  
-   OMS_O01_231_GLO_DEF  
  
-   ORD_O02_231_GLO_DEF  
  
-   ORN_O02_231_GLO_DEF  
  
-   ORS_O02_231_GLO_DEF  
  
## <a name="see-also"></a>参照  
 [既知の問題](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)
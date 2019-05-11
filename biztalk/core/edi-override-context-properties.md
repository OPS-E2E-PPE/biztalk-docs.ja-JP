---
title: EDI 上書きコンテキストのプロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d78cd56f-1e34-4503-8ee1-93b52137097f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fcbbc5e5b8ced9c957866ceb808dbebc4a16206f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389174"
---
# <a name="edi-override-context-properties"></a>EDI 上書きコンテキストのプロパティ
EdiOverride グローバル プロパティ スキーマのメッセージ コンテキスト プロパティは、実行時に EDI エンベロープ値を上書きできます。 これらのメッセージ コンテキスト プロパティは、Microsoft.BizTalk.Edi.BaseArtifacts アセンブリの edi-properties.xsd で定義されます。 プロパティの名前空間は`http://schemas.microsoft.com/BizTalk/2006/edi-properties`します。  
  
 EdiOverride コンテキスト プロパティは、Microsoft.BizTalk.Edi.BaseArtifacts アセンブリへの参照がオーケストレーション プロジェクトに追加されている限り、オーケストレーションで入手できます。  
  
|名前|型|説明|  
|----------|----------|-----------------|  
|OverrideEDIHeader|boolean|True の場合、EDI 送信パイプラインは、EdiOverride プロパティ コレクションに値を使用して EDI エンベロープを構築しようとします。|  
|ISA01|string|承認情報修飾子 (X12)|  
|ISA02|string|承認情報 (X12)|  
|ISA03|string|セキュリティ情報修飾子 (X12)|  
|ISA04|string|セキュリティ情報 (X12)|  
|ISA05|string|インターチェンジ送信者の修飾子 (X12)|  
|ISA06|string|インターチェンジの送信者 ID (X12)|  
|ISA07|string|インターチェンジ受信者の修飾子 (X12)|  
|ISA08|string|インターチェンジ受信者 ID (X12)|  
|ISA09|string|(X12) のインターチェンジ日付<br /><br /> このフィールドは、日付形式ではなく実際の日付値を含める必要があります。|  
|ISA10|string|(X12) のインターチェンジ時刻<br /><br /> このフィールドは、日付値ではなく、実際の時刻の値を含める必要があります。|  
|ISA11|string|インターチェンジ制御標準識別子 (X12)|  
|[ISA12]|string|インターチェンジ制御バージョン番号 (X12)|  
|ISA13|string|インターチェンジ制御番号 (X12)<br /><br /> インターチェンジ制御番号がオーバーライドされた場合、対応するインターチェンジ トレーラー セグメント (IEA) は、指定した値に一致するように設定されます。|  
|[ISA14]|string|受信確認要求 (X12)|  
|ISA15|string|テスト インジケーター (X12)|  
|ISA16|string|コンポーネント要素区切り記号 (X12)|  
|GS01|string|機能識別コード (X12)|  
|GS02|string|アプリケーション送信者コード (X12)|  
|GS03|string|アプリケーション受信者コード (X12)|  
|GS04|string|日付 (X12)<br /><br /> このフィールドは、日付形式ではなく実際の日付値を含める必要があります。<br /><br /> この値は、CCYYMMDD または YYMMDD の形式で指定する必要があります。 指定された日付は、パーティのプロパティで選択されているものと異なる形式で日付が提供されている場合でも使用されます。|  
|GS05|string|(X12) 時間<br /><br /> このフィールドは、時刻の形式ではなく、実際の時刻の値を含める必要があります。<br /><br /> この値は、HHMM、HHMMSS、または HHMMSSdd の形式で指定する必要があります。 指定された時間は、時間がパーティのプロパティで選択されているものと異なる形式で提供されている場合でも使用されます。|  
|GS06|string|グループ制御番号 (X12)<br /><br /> グループ制御番号がオーバーライドされると、GE セグメントに対応するフィールドが指定された値に一致するように設定されます。|  
|GS07|string|担当機関コード (X12)|  
|GS08|string|バージョン/リリース/業界識別コード (X12)|  
|ST02|string|トランザクション セット制御番号 (X12)<br /><br /> トランザクション セット制御番号がオーバーライドされた場合、トランザクション セット トレーラー セグメント (SE) に対応するフィールドはこの値に一致するように設定されます。|  
|GenerateUNA|boolean|EDI 送信パイプラインが送信 EDIFACT ドキュメントの UNA セグメントを作成するかどうかを決定します。<br /><br /> OverrideEdiHeader が true で generateuna も場合は、UNA セグメントが生成されます。 OverrideEdiHeader が true の場合、UNA の生成が false の場合は、UNA セグメントは生成されません。<br /><br /> UNA セグメントの値は次の順序で決定されます。<br /><br /> -EdiOverride コンテキスト プロパティ、すべての UNA プロパティが存在する場合。<br />ない場合は、すべてのコンテキスト プロパティが存在して、UNA セグメントを生成は、パーティのプロパティをコンテキスト プロパティとパーティのプロパティの組み合わせで確認います。<br />-すべてのコンテキスト プロパティが存在して、UNA セグメントを生成がパーティのプロパティ、コンテキスト プロパティと標準 UNA 値の組み合わせでオフになってかどうか**に注意してください。** OverrideEdiHeader が false の場合は、このフィールドを指定しても効果がありません。|  
|UNA1|string|コンポーネント データ要素区切り記号 (EDIFACT)|  
|UNA2|string|データ要素区切り記号 (EDIFACT)|  
|UNA3|string|小数点記号 (EDIFACT)|  
|UNA4|string|リリース文字 (EDIFACT)|  
|UNA5|string|繰り返し区切り記号 (EDIFACT)|  
|UNA6|string|セグメント終端記号 (EDIFACT)|  
|UNA6Suffix|string|セグメント終端記号サフィックス (EDIFACT)|  
|UNB1_1|string|構文識別子 (EDIFACT)|  
|UNB1_2|string|構文のバージョン番号 (EDIFACT)|  
|UNB10|string|通信アグリーメント ID (EDIFACT)|  
|UNB11|string|テスト インジケーター (EDIFACT)|  
|UNB2_1|string|送信者 Id (EDIFACT)|  
|UNB2_2|string|パートナー識別コードの修飾子 (EDIFACT)|  
|UNB2_3|string|(EDIFACT) の逆ルーティングのアドレス|  
|UNB3_1|string|受信者 Id (EDIFACT)|  
|UNB3_2|string|パートナー識別コードの修飾子 (EDIFACT)|  
|UNB3_3|string|ルーティングのアドレス (EDIFACT)|  
|UNB4_1|string|日付 (EDIFACT)<br /><br /> このフィールドは、日付形式ではなく実際の日付値を含める必要があります。|  
|UNB4_2|string|時刻 (EDIFACT)<br /><br /> このフィールドは、時刻の形式ではなく、実際の時刻の値を含める必要があります。|  
|UNB5|string|インターチェンジ制御参照 (EDIFACT)<br /><br /> インターチェンジ制御参照がオーバーライドされると、インターチェンジ トレーラー セグメント (UNZ) 内の制御番号は、指定した値に一致するように設定されます。|  
|UNB6_1|string|受信者の参照/パスワード (EDIFACT)|  
|UNB7|string|アプリケーション参照 (EDIFACT)|  
|UNB8|string|処理優先度コード (EDIFACT)|  
|[UNB9]|string|受信確認要求 (EDIFACT)|  
|GenerateUNG|boolean|EDI 送信パイプラインが送信 EDIFACT ドキュメントの UNG セグメントを作成するかどうかを決定します。<br /><br /> OverrideEdiHeader が true で GenerateUNG が true の場合は、UNG セグメントが生成されます。 OverrideEdiHeader が true で generateung が false、UNG セグメントは生成されません。<br /><br /> UNG セグメントの値は次の順序で決定されます。<br /><br /> -EdiOverride コンテキスト プロパティ、すべての UNG プロパティが存在する場合。<br />ない場合は、すべてのコンテキスト プロパティが存在して生成の UNG セグメントのパーティのプロパティをコンテキスト プロパティとパーティのプロパティの組み合わせがチェックインします。<br />ですべてのコンテキスト プロパティが存在して、生成 UNG セグメントをパーティのプロパティ、コンテキスト プロパティと標準 UNA 値の組み合わせでチェック ボックスがオフない場合**に注意してください。** OverrideEdiHeader が false の場合は、このフィールドを指定しても効果がありません。|  
|UNG1|string|メッセージ グループ Id (EDIFACT)|  
|UNG2_1|string|アプリケーション送信者 Id (EDIFACT)|  
|UNG2_2|string|識別コードの修飾子 (EDIFACT)|  
|UNG3_1|string|アプリケーション受信者 Id (EDIFACT)|  
|UNG3_2|string|識別コードの修飾子 (EDIFACT)|  
|UNG4_1|string|準備 (EDIFACT) の日付<br /><br /> このフィールドは、日付形式ではなく実際の日付値を含める必要があります。|  
|UNG4_2|string|準備 (EDIFACT) の時刻<br /><br /> このフィールドは、時刻の形式ではなく、実際の時刻の値を含める必要があります。|  
|UNG5|string|グループ参照番号 (EDIFACT)<br /><br /> グループ参照番号がオーバーライドされた場合、グループ トレーラー セグメント (UNE) の対応するフィールドは、指定した値に一致するように設定します。|  
|UNG6|string|制御機関コード (EDIFACT)|  
|UNG7_1|string|メッセージのバージョン番号 (EDIFACT)|  
|UNG7_2|string|メッセージのリリース番号 (EDIFACT)|  
|UNG7_3|string|関連付けの割り当てコード (EDIFACT)|  
|UNG8|string|アプリケーションのパスワード (EDIFACT)|  
|UNH1|string|メッセージ参照番号 (EDIFACT)<br /><br /> メッセージ参照番号がオーバーライドされると、メッセージ トレーラー セグメント (UNT) の対応するフィールドは、この値に一致するように設定されます。|  
  
## <a name="edioverride-context-property-usage"></a>EDIOverride コンテキスト プロパティの使用  
 場合、 **OverrideEdiHeader**コンテキスト プロパティが true、送信メッセージの EDI エンベロープを作成する、EDIOverride コンテキスト プロパティで指定された値が使用されます。 EDIOverride コンテキスト プロパティの値が指定されていない場合、対応するパーティまたはグローバル プロパティが使用されます。  
  
 EDIOverride コンテキスト プロパティに指定された値は、X12 または EDIFACT 標準およびすべてのサービス スキーマ拡張に従って有効である必要があります。  
  
- フィールドには、サービス スキーマを拡張機能を含め、そのフィールド型の有効な値を含める必要があります。  
  
- 制御番号は有効な型でなければなりませんが、既存のパーティ設定での順序である必要はありません。  
  
- 日付と時刻のフィールドは、日付と時刻の値が含まれ、値の形式がパーティ設定で定義されている形式と一致しない場合でも、関連する EDI 標準に従って有効である必要があります。  
  
  一部の EDIOverride コンテキスト プロパティは、EDI 送信パイプラインによって送信されるメッセージが 1 つのトランザクションまたはバッチの場合にのみサポートされます。 次の表では、メッセージの種類ごとのサポートされているコンテキスト プロパティを示します。  
  
|送信される EDI トランザクション|サポートされる EDIOverride コンテキスト プロパティ|  
|--------------------------------|----------------------------------------------|  
|単一のトランザクション セット|-すべての Isa<br />-すべての Gs<br />-ST02<br />-GenerateUNA<br />-すべての Una<br />-すべての Unb<br />-   GenerateUNG<br />-すべての Ung<br />-   UNH1|  
|バッチ処理オーケストレーションによって公開されたバッチのトランザクション セットまたは EDI 受信パイプラインによって発行されたバッチのバッチをトランザクション セット|-すべての Isa<br />-GS04<br />-GS05<br />-GenerateUNA<br />-すべての Una<br />-すべての Unb<br />-   GenerateUNG<br />-UNG4.1:<br />-UNG4.2:|  
  
 ただし、バッチ処理オーケストレーションは、ST01 と UNH1 EDIOverride コンテキスト プロパティのみをサポート、EDIOverride コンテキスト プロパティをバッチ処理は、メッセージに適用もできます。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server EDI ソリューションの開発と構成](../core/developing-and-configuring-biztalk-server-edi-solutions.md)
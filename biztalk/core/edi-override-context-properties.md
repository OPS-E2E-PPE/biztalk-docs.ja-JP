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
ms.openlocfilehash: 2b66b9a2d6c2a601f40f276692ba53b732c95ec6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986571"
---
# <a name="edi-override-context-properties"></a>EDI オーバーライドコンテキストのプロパティ
EdiOverride グローバル プロパティ スキーマのメッセージ コンテキスト プロパティを使用すると、EDI エンベロープの値を実行時にオーバーライドすることができます。 これらのメッセージ コンテキスト プロパティは、Microsoft.BizTalk.Edi.BaseArtifacts アセンブリの edi-properties.xsd で定義されています。 これらのプロパティの名前空間は `http://schemas.microsoft.com/BizTalk/2006/edi-properties` です。  
  
 EdiOverride のコンテキスト プロパティは、Microsoft.BizTalk.Edi.BaseArtifacts アセンブリへの参照がオーケストレーション プロジェクトに追加されている限り、オーケストレーションでも使用できます。  
  
|名前|型|説明|  
|----------|----------|-----------------|  
|OverrideEDIHeader|boolean|true の場合、EDI 送信パイプラインは、EdiOverride プロパティ コレクションの値を使用して EDI エンベロープの作成を試行します。|  
|ISA01|string|認証情報の修飾子 (X12)|  
|ISA02|string|認証情報 (X12)|  
|ISA03|string|セキュリティ情報の修飾子 (X12)|  
|ISA04|string|セキュリティ情報 (X12)|  
|ISA05|string|インターチェンジ送信者の修飾子 (X12)|  
|ISA06|string|インターチェンジ送信者の ID (X12)|  
|ISA07|string|インターチェンジ受信者の修飾子 (X12)|  
|ISA08|string|インターチェンジ受信者の ID (X12)|  
|ISA09|string|インターチェンジの日付 (X12)<br /><br /> このフィールドには、日付形式ではなく実際の日付を指定します。|  
|ISA10|string|インターチェンジの時刻 (X12)<br /><br /> このフィールドには、日付の値ではなく実際の時刻の値を指定します。|  
|ISA11|string|インターチェンジ制御標準識別子 (X12)|  
|ISA12|string|インターチェンジ制御バージョン番号 (X12)|  
|ISA13|string|インターチェンジ制御番号 (X12)<br /><br /> インターチェンジ制御番号をオーバーライドすると、対応するインターチェンジ トレーラー セグメント (IEA) が指定した値に合わせて設定されます。|  
|ISA14|string|受信確認要求 (X12)|  
|ISA15|string|テスト インジケーター (X12)|  
|ISA16|string|コンポーネント要素区切り記号 (X12)|  
|GS01|string|機能識別コード (X12)|  
|GS02|string|アプリケーション送信者コード (X12)|  
|GS03|string|アプリケーション受信者コード (X12)|  
|GS04|string|日付 (X12)<br /><br /> このフィールドには、日付形式ではなく実際の日付を指定します。<br /><br /> この値は、CCYYMMDD または YYMMDD の形式で指定する必要があります。 パーティのプロパティで選択されている形式と異なる形式で日付を指定しても、ここで指定した日付が使用されます。|  
|GS05|string|時刻 (X12)<br /><br /> このフィールドには、時刻形式ではなく実際の時刻を指定します。<br /><br /> この値は、HHMM、HHMMSS、または HHMMSSdd の形式で指定する必要があります。 パーティのプロパティで選択されている形式と異なる形式で時刻を指定しても、ここで指定した時刻が使用されます。|  
|GS06|string|グループ制御番号 (X12)<br /><br /> グループ制御番号をオーバーライドすると、対応する GE セグメントのフィールドが指定した値に合わせて設定されます。|  
|GS07|string|担当機関コード (X12)|  
|GS08|string|バージョン/リリース/業界識別コード (X12)|  
|ST02|string|トランザクション セット制御番号 (X12)<br /><br /> トランザクション セット制御番号をオーバーライドすると、対応するトランザクション セットのトレーラー セグメント (SE) のフィールドが指定した値に合わせて設定されます。|  
|GenerateUNA|boolean|EDI 送信パイプラインで送信 EDIFACT ドキュメントの UNA セグメントを作成するかどうかを決定します。<br /><br /> OverrideEdiHeader が true で GenerateUNA も true の場合、UNA セグメントが生成されます。 OverrideEdiHeader が true で GenerateUNA が false の場合、UNA セグメントは生成されません。<br /><br /> UNA セグメントの値は次の順序で決定されます。<br /><br /> -EdiOverride コンテキスト プロパティ、すべての UNA プロパティが存在する場合。<br />ない場合は、すべてのコンテキスト プロパティが存在して、UNA セグメントを生成は、パーティのプロパティをコンテキスト プロパティとパーティのプロパティの組み合わせで確認います。<br />-すべてのコンテキスト プロパティが存在して、UNA セグメントを生成がパーティのプロパティ、コンテキスト プロパティと標準 UNA 値の組み合わせでオフになってかどうか**注:** このフィールドには効果がない OverrideEdiHeader が false の場合。|  
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
|UNB2_1|string|送信者 ID (EDIFACT)|  
|UNB2_2|string|パートナー識別コードの修飾子 (EDIFACT)|  
|UNB2_3|string|逆ルーティングのアドレス (EDIFACT)|  
|UNB3_1|string|受信者 ID (EDIFACT)|  
|UNB3_2|string|パートナー識別コードの修飾子 (EDIFACT)|  
|UNB3_3|string|ルーティングのアドレス (EDIFACT)|  
|UNB4_1|string|日付 (EDIFACT)<br /><br /> このフィールドには、日付形式ではなく実際の日付を指定します。|  
|UNB4_2|string|時刻 (EDIFACT)<br /><br /> このフィールドには、時刻形式ではなく実際の時刻を指定します。|  
|UNB5|string|インターチェンジ制御参照 (EDIFACT)<br /><br /> インターチェンジ制御参照をオーバーライドすると、インターチェンジ トレーラー セグメント (UNZ) の制御番号が指定された値と一致するように設定されます。|  
|UNB6_1|string|受信者の参照/パスワード (EDIFACT)|  
|UNB7|string|アプリケーション参照 (EDIFACT)|  
|UNB8|string|処理優先度コード (EDIFACT)|  
|UNB9|string|受信確認要求 (EDIFACT)|  
|GenerateUNG|boolean|EDI 送信パイプラインで送信 EDIFACT ドキュメントの UNG セグメントを作成するかどうかを決定します。<br /><br /> OverrideEdiHeader が true で GenerateUNG も true の場合、UNG セグメントが生成されます。 OverrideEdiHeader が true で GenerateUNG が false の場合、UNG セグメントは生成されません。<br /><br /> UNG セグメントの値は次の順序で決定されます。<br /><br /> -EdiOverride コンテキスト プロパティ、すべての UNG プロパティが存在する場合。<br />ない場合は、すべてのコンテキスト プロパティが存在して生成の UNG セグメントのパーティのプロパティをコンテキスト プロパティとパーティのプロパティの組み合わせがチェックインします。<br />ですべてのコンテキスト プロパティが存在して、生成 UNG セグメントをパーティのプロパティ、コンテキスト プロパティと標準 UNA 値の組み合わせでチェック ボックスがオフない場合**注:** このフィールドには効果がない OverrideEdiHeader が false の場合。|  
|[UNG1]|string|メッセージ グループ ID (EDIFACT)|  
|UNG2_1|string|アプリケーション送信者 ID (EDIFACT)|  
|UNG2_2|string|識別コードの修飾子 (EDIFACT)|  
|UNG3_1|string|アプリケーション受信者 ID (EDIFACT)|  
|UNG3_2|string|識別コードの修飾子 (EDIFACT)|  
|UNG4_1|string|準備の日付 (EDIFACT)<br /><br /> このフィールドには、日付形式ではなく実際の日付を指定します。|  
|UNG4_2|string|準備の時刻 (EDIFACT)<br /><br /> このフィールドには、時刻形式ではなく実際の時刻を指定します。|  
|UNG5|string|グループ参照番号 (EDIFACT)<br /><br /> グループ参照番号をオーバーライドすると、グループ トレーラー セグメント (UNE) の対応するフィールドが指定された値と一致するように設定されます。|  
|[UNG6]|string|制御機関コード (EDIFACT)|  
|UNG7_1|string|メッセージのバージョン番号 (EDIFACT)|  
|UNG7_2|string|メッセージのリリース番号 (EDIFACT)|  
|UNG7_3|string|関連付けの割り当てコード (EDIFACT)|  
|[UNG8]|string|アプリケーション パスワード (EDIFACT)|  
|UNH1|string|メッセージ参照番号 (EDIFACT)<br /><br /> メッセージ参照番号をオーバーライドすると、メッセージ トレーラー セグメント (UNT) の対応するフィールドがこの値と一致するように設定されます。|  
  
## <a name="edioverride-context-property-usage"></a>EDIOverride コンテキスト プロパティの使用法  
 場合、 **OverrideEdiHeader**コンテキスト プロパティが true、送信メッセージの EDI エンベロープを作成する、EDIOverride コンテキスト プロパティで指定された値が使用されます。 EDIOverride コンテキスト プロパティに値が指定されていない場合は、対応する "パーティ" プロパティまたは "グローバル" プロパティが使用されます。  
  
 EDIOverride コンテキスト プロパティに指定する値は、X12 標準または EDIFACT 標準およびサービス スキーマ拡張に準拠した有効な値である必要があります。  
  
- フィールドには、サービス スキーマの拡張を含め、そのフィールドの種類に有効な値を指定する必要があります。  
  
- 制御番号は有効な型で指定されている必要がありますが、既存のパーティの設定の続きの番号である必要はありません。  
  
- 日付および時刻フィールドは、日付および時刻の値を含み、値の形式がパーティの設定で定義された形式と一致しなくても、関連する EDI 標準に準拠した有効な値である必要があります。  
  
  一部の EDIOverride コンテキスト プロパティは、EDI 送信パイプラインによって送信されるメッセージが単一のトランザクションまたはバッチである場合のみサポートされます。 次の表は、それぞれのメッセージの種類でサポートされるコンテキスト プロパティの一覧です。  
  
|送信される EDI トランザクション|サポートされる EDIOverride コンテキスト プロパティ|  
|--------------------------------|----------------------------------------------|  
|単一のトランザクション セット|-すべての Isa<br />-すべての Gs<br />-ST02<br />-GenerateUNA<br />-すべての Una<br />-すべての Unb<br />-GenerateUNG<br />-すべての Ung<br />-UNH1|  
|バッチ処理オーケストレーションによって公開されるバッチ トランザクション セット、または EDI 受信パイプラインによって公開される Batch-in-Batch-Out トランザクション セット|-すべての Isa<br />-GS04<br />-GS05<br />-GenerateUNA<br />-すべての Una<br />-すべての Unb<br />-GenerateUNG<br />-UNG4.1:<br />-UNG4.2:|  
  
 EDIOverride コンテキスト プロパティは、バッチ処理されるメッセージにも適用できますが、バッチ処理オーケストレーションでサポートされる EDIOverride コンテキスト プロパティは ST01 と UNH1 だけです。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server EDI ソリューションの開発と構成](../core/developing-and-configuring-biztalk-server-edi-solutions.md)
---
title: BTAHL7 によるメッセージのルーティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- routing, about routing
- routing, messages
- messages, routing
- BTAHL7, message routing
ms.assetid: 555696c7-6023-44eb-b13d-cf7527bbc92f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c64cd0620dacf835d3765510ea74c2a8cc80c4a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999291"
---
# <a name="how-btahl7-routes-messages"></a>BTAHL7 によるメッセージのルーティング方法
Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) メッセージの処理の Microsoft の機能を活用して[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]が HL7 メッセージングの要件に固有のいくつかの方法で拡張することもできます。  

## <a name="routing-overview"></a>ルーティングの概要

HL7 は、基幹業務 (LOB) システムからメッセージを受信し、MLLP アダプターを使用してそれらを受信する可能性があります。 LOB システムに MLLP アダプターを接続する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]over TCP ポート、およびし MLLP アダプターにメッセージを送信します。

**[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]と以前のバージョン**、HL7 MLLP 受信 MLLP への接続に、リモート LOB システムのトランスポート アダプター待機します。 接続すると、リモート LOB システム、LOB システム送信に MLLP を使用して、メッセージ、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 具体的な内容は次のとおりです。 

1. リモートの LOB システムは、ローカルの MLLP アダプターに接続する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]TCP ポートを使用 
2. 受信場所が、BTA4HL7 MLLP アダプターは、接続を受け入れます 
3. リモートの LOB システムに 1 つまたは複数のメッセージを配信します。 
4. リモートの LOB システムを切断します。

**[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]以降のバージョン**、MLLP アダプターで LOB システムへの接続が開始され、MLLP への LOB システム プッシュ メッセージを受信します。 つまり、リモート LOB システムは、メッセージングを MLLP に送信する前に、接続の待機します。 具体的な内容は次のとおりです。 

1. ローカル[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]TCP ポートを使用して、リモート LOB システムに接続します。 
2. BTA4HL7 接続の受信場所の MLLP アダプターを開始します 
3. リモートの LOB システムに 1 つまたは複数のメッセージを配信します。 
4. リモートの LOB システムを切断します。 

旧バージョンとの互換性のためには、リモート LOB システムが接続を開始元の既定の動作使用できます。 このオプションは、MLLP で構成可能な受信場所のプロパティ。 
 
HL7 メッセージを受信すると、HL7 に送信し、受信パイプライン。 このパイプラインでは、HL7 の逆アセンブラーは、メッセージを解析し、適切なスキーマ定義と検証の構成に従ってメッセージを検証します。 (成功またはエラー)、この時点では、受信確認メッセージがあります、HL7 が生成されたメッセージと関連する受信確認の構成の有効性に従ってします。 ここでは、メッセージ インスタンスと省略可能な受信確認の処理およびルーティングをさらに、メッセージ ボックス データベースには、パイプラインが送信されます。  
  
 メッセージ インスタンスが、メッセージ ボックス データベースが到着すると[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]フィルターに基づくサブスクリプションを確認し、HL7 送信パイプラインを通じて送信ポート (MLLP ポート可能性があります) を 1 つまたは複数のメッセージをルーティングします。 送信パイプラインは、適切なスキーマの定義と検証の構成に従ってメッセージ インスタンスを検証可能性があります。 検証を加え、送信メッセージの MSH セグメントで特定のフィールド値をオーバーライドすることです。 この上書き機能は、メッセージにサブスクライブしている複数のポートと受信側アプリケーションごとに MSH のセグメント値内で一意の期待場合に特に便利です。  
  
 他のすべてではもちろん、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]送信し、受信ポートの機能が使用可能 MLLP 送信ポートのパラメーターなど、選択したポートの種類に固有のいくつかの機能と共に、HL7 メッセージになります。 関連する例[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]機能は、送信メッセージに変換マップを適用することになります。  
  
## <a name="how-routing-works"></a>ルーティングの動作

[!INCLUDE[btaBTAHL7NoNumber_md](../../includes/btabtahl7nonumber-md.md)]ルート HL7 メッセージに従って、メッセージ ボックス データベースを管理するサブスクリプションのインスタンス。 これらのサブスクリプションでは、送信ポートごとに定義されたフィルターを使用します。 ベースのルーティング フィルター例にはが含まれます受信ポートの ID や HL7 メッセージの種類 (ADT ^ A03、たとえば) アプリケーション (MSH3.1 値) を送信します。  
  
 設定するだけでなく[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]として HL7 メッセージ インスタンスに影響を与える HL7 に固有のメッセージング構成を実行する必要があるサブスクリプションの場合、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]にルーティングします。 この追加の構成では、一意の HL7 検証規則の受信確認の自動生成および MSH 値をオーバーライドする機能を適用することができます。 [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] この構成はパーティ レベルで適用します。 BizTalk エクスプ ローラーでパーティを定義し、関連する HL7 構成内で実行する必要がある[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]構成エクスプ ローラー。  
  
 複数の送信ポートのメッセージをサブスクライブするには、一意の HL7 メッセージングの構成 (たとえば、検証または MSH の上書き) を適用するには、パーティ間の関連付けを作成および送信ポートを必要があります。 BizTalk エクスプ ローラーでパーティのプロパティとしては、パーティの送信ポートの関連付けを構成します。  
  
 複数の送信ポートにメッセージをルーティング HL7 必要がありますまたは複数の送信ポートに一意の HL7 処理構成を適用しない、送信ポートをパーティに関連付ける手順から除外できます。 この場合、 [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] HL7 メッセージ (MSH 3.1) で、受信側のアプリケーション フィールドを介して、HL7 メッセージング構成をパーティを関連付けます。 このような状況が HL7 interrogative (要求/応答) で発生する最も可能性の高いメッセージ交換します。  
  
## <a name="see-also"></a>参照  
 [メッセージの検証](../../adapters-and-accelerators/accelerator-hl7/message-validation.md)
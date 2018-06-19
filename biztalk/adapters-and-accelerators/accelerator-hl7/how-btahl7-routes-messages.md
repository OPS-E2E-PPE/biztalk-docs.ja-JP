---
title: BTAHL7 でメッセージをルーティングする方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 61dd223a014ae8ea7de35d8d73f1a7cf7ef35449
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22205098"
---
# <a name="how-btahl7-routes-messages"></a>BTAHL7 でメッセージをルーティングする方法
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)])、メッセージ処理の機能を活用して[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、HL7 メッセージング要件に固有のいくつかの方法で拡張することも、します。  

## <a name="routing-overview"></a>ルーティングの概要

HL7 は、基幹業務 (LOB) システムからメッセージを受信し、MLLP アダプターを使用してそれらを受け取ることがあります。 LOB システムに MLLP アダプターを接続する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]TCP ポート、および、送信メッセージ MLLP アダプターを経由します。

 **[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]と以前のバージョン**、HL7 MLLP の受信 MLLP に接続するリモートの LOB システムのトランスポート アダプターを待機します。 リモートの LOB システム接続するいると、LOB システム メッセージを送信しますに MLLP を使用して、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 具体的な内容は次のとおりです。 

1. ローカル MLLP アダプターに接続するリモートの LOB システム[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]TCP ポートを使用します。 
2. 受信場所が、BTA4HL7 MLLP アダプターは、接続を受け入れます 
3. 1 つまたは複数のメッセージを配信するリモートの LOB システム 
4. リモートの LOB システムの接続が切断します。

 **[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]以降のバージョン**MLLP アダプターによって、LOB システムへの接続が開始され、MLLP への LOB システム プッシュ メッセージを受信し、します。 つまり、リモートの LOB システム待機 MLLP にメッセージングを送信する前に接続します。 具体的な内容は次のとおりです。 

1. ローカル[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]TCP ポートを使用してリモートの LOB システムに接続するには 
2. 受信場所 MLLP アダプターを開始、接続が、BTA4HL7 
3. 1 つまたは複数のメッセージを配信するリモートの LOB システム 
4. リモートの LOB システムの接続が切断します。 

下位互換性を行うこともできます、元の既定の動作、リモートの LOB システムが接続を開始します。 このオプションは構成可能で、MLLP 受信場所のプロパティです。 
 
HL7 メッセージを受信すると、HL7 に送信し、受信パイプラインです。 このパイプラインでは、HL7 逆アセンブラーは、メッセージを解析し、適切なスキーマ定義と検証の構成に従ってメッセージを検証します。 (成功またはエラー)、この時点では、受信確認メッセージがあります、HL7 が生成されたメッセージと関連する受信確認の構成の有効性に従ってします。 ここでは、メッセージ インスタンスと省略可能な受信確認をさらに処理し、ルーティング、メッセージ ボックス データベースには、パイプラインが送信されます。  
  
 メッセージ ボックス データベースに到着するメッセージ インスタンスと[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]フィルターに基づくサブスクリプションをチェックし、HL7 送信パイプラインを通じて送信ポート (MLLP ポート可能性があります) を 1 つまたは複数のメッセージをルーティングします。 送信パイプラインは、適切なスキーマ定義と検証の構成に従ってメッセージ インスタンスを検証可能性があります。 検証を加え、送信メッセージの MSH セグメントでは、特定のフィールド値をオーバーライドすることです。 この上書き機能は、複数のポートがメッセージにサブスクライブしているし、各受信側のアプリケーションが MSH セグメント値内で一意の期待場合に特に便利です。  
  
 もちろん、その他のすべて[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ポートの送受信を行う機能は MLLP 送信ポートのパラメーターなど、選択したポートの種類に対して一意である可能性がありますをいくつかの機能に加えて、HL7 メッセージに使用できます。 関連する例[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]機能は、送信メッセージに、変換マップを適用する機能になります。  
  
## <a name="how-routing-works"></a>ルーティングのしくみ

[!INCLUDE[btaBTAHL7NoNumber_md](../../includes/btabtahl7nonumber-md.md)]ルート HL7 メッセージに従って、メッセージ ボックス データベースを管理するサブスクリプションのインスタンス。 これらのサブスクリプションでは、送信ポートごとに定義されたフィルターを使用します。 ベースのルーティングの例のフィルターを含めることが受信ポートの ID および HL7 メッセージの種類 (ADT ^ 例については、A03) アプリケーション (MSH3.1 値) を送信します。  
  
 設定するだけでなく[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]として HL7 メッセージ インスタンスに影響を与える HL7 に固有のメッセージング構成を実行する必要があります、サブスクリプション[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]それにルーティングします。 この追加の構成では、一意の HL7 検証規則、受信確認の自動生成 MSH 値を上書きする機能を適用することができます。 [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]この構成はパーティ レベルで適用します。 BizTalk エクスプ ローラーでパーティを定義し、内で関連する HL7 構成を実行する必要があります[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]構成エクスプ ローラー。  
  
 メッセージをサブスクライブする複数の送信ポートに一意の HL7 メッセージの構成 (たとえば、検証または MSH オーバーライド) を適用するには、パーティ間の関連付けを作成し、ポートを送信する必要があります。 BizTalk エクスプ ローラーでパーティのプロパティとしては、パーティの送信ポートの関連付けを構成します。  
  
 複数の送信ポートにメッセージをルーティング HL7 必要または複数の送信ポートに一意の HL7 処理の構成を適用しない、送信ポートとパーティの関連付けの手順を除外できます。 この場合、 [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] HL7 メッセージ (MSH 3.1) の受信側のアプリケーション フィールドを介して、HL7 メッセージング構成に、パーティを関連付けます。 この状況は、HL7 interrogative (要求/応答) に発生する最も可能性の高いメッセージ交換します。  
  
## <a name="see-also"></a>参照  
 [メッセージの検証](../../adapters-and-accelerators/accelerator-hl7/message-validation.md)
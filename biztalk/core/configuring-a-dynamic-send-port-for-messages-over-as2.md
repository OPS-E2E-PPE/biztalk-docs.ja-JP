---
title: AS2 経由でメッセージを動的送信ポートの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 246d64e8-70ca-48f4-8b72-d43b0964dbb4
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af1952947120a6f90310244f7ef17ee6fc5810d1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356397"
---
# <a name="configuring-a-dynamic-send-port-for-messages-over-as2"></a>AS2 経由でのメッセージの動的送信ポートの構成
このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成し、動的送信ポートを経由して AS2 メッセージを送信する方法について説明します。 この構成作業では、動的送信ポートを作成し、バックエンド アプリケーションを構成して該当するコンテキスト プロパティを設定します。 動的送信ポートを作成して AS2 メッセージを送信する場合、送信ポートが動作するように特定のプロパティを昇格する必要があります。 詳細については、次を参照してください。[送信ポートを動的にメッセージを BizTalk Server AS2 の送信を構成](../core/configuring-a-dynamic-send-port-for-messages-over-as2.md#BKMK_Proc)以下。  
  
 動的送信ポートを使用すると、パーティの構成をハードコーディングせずに、複数のパーティにメッセージを送信できます。 メッセージの送信に使用するアグリーメントおよび送信先は、コンテキスト プロパティを使用して動的に決定されます。 個々の顧客用に静的送信ポートを作成する必要はありません。  
  
 EDI メッセージまたは非 EDI メッセージを持つ AS2 メッセージや EDI 受信確認を送信するには、次のように構成された動的 HTTP 応答送信ポートを作成します。  
  
|場所|プロパティ|設定|  
|--------------|--------------|-------------|  
|**送信ポートのプロパティ:[全般]**|ポートの種類|-動的な送信請求-応答 (場合に mdn を要求する**受信確認 (Mdn)** 一方向アグリーメント タブでページが選択されている)<br /><br /> -動的な一方向送信ポート (場合に mdn を要求する**受信確認 (Mdn)** 一方向アグリーメント タブでページがクリアされます)|  
|**送信ポートのプロパティ:[全般]**|[送信パイプライン]|-AS2EdiSend (EDI エンコード メッセージの場合)<br /><br /> -AS2Send (非 EDI メッセージの場合)|  
|**送信ポートのプロパティ:[全般]**|受信パイプライン。<br /><br /> (場合に mdn を要求する**受信確認 (Mdn)** 一方向アグリーメント タブでページが選択されている)|AS2Receive (動的な送信請求応答の送信ポートの場合)|  
|**送信ポートのプロパティ:フィルター**|プロパティ|BTS.MessageType|  
|**送信ポートのプロパティ:フィルター**|演算子|==|  
|**送信ポートのプロパティ:フィルター**|値|- `http://schemas.microsoft.com/BizTalk/EDI/X12/2006#<schema name>` (の EDI メッセージの場合)<br /><br /> - `http://schemas.microsoft.com/Edi/X12#X12_<997 or TA1>_Root` (x12 受信確認)<br /><br /> - `http://schemas.microsoft.com/Edi/Efact#Efact_Contrl_Root` (EDIFACT 受信確認) を|  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
##  <a name="BKMK_Proc"></a> 送信ポートを動的にメッセージを BizTalk Server AS2 の送信を構成  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、前のように構成された、動的な一方向の送信ポート (MDN が要求されていない場合) または動的な送信請求応答の送信ポート (MDN が要求されている場合) を作成します。  
  
2. このメッセージに該当するアグリーメントに対して、AS2 プロパティおよび EDI プロパティを設定する必要があります。  
  
3. 次のプロパティをメッセージ コンテキストに昇格します。  
  
   -   `BTS.MessageType`  
  
   -   `EdiIntAS.MessageID`  
  
4. 次のプロパティをメッセージ コンテキストに書き込む機能をバックエンド アプリケーションに追加し、プロパティに適切な値を設定します。  
  
   -   `EdiIntAS.AS2To`  
  
   -   `BTS.OutboundTransportLocation`  
  
   -   `HTTP.EnableChunkedEncoding`  
  
   -   `BTS.EncryptionCert`  
  
   > [!NOTE]
   >  動的送信ポートが正しく機能するように、`AS2To` および `OutboundTransportLocation` の各コンテキスト プロパティをメッセージ コンテキストに書き込む必要があります。 `AS2To` プロパティは、送信メッセージの処理に使用するアグリーメントをポートで決定するために必要です。`OutboundTransportLocation` プロパティは、メッセージの送信先を送信ポートで決定するために必要です。 詳細については、次を参照してください。[送信 AS2 メッセージを生成する](../core/generating-an-outgoing-as2-message.md)します。  
  
## <a name="functionality"></a>機能  
 動的送信ポートとパイプラインは次の操作を実行して、AS2 経由で同期 EDI メッセージ、非 EDI メッセージ、または受信確認を送信し、返された MDN を処理します。  
  
- EDI メッセージを送信する場合は、`BTS.MessageType` プロパティのフィルター処理を `http://schemas.microsoft.com/BizTalk/EDI/X12/2006 namespace` のメッセージ スキーマに設定して (たとえば、864 メッセージの場合は X12_00401_864)、EDI メッセージを取得します。  
  
- EDI 受信確認を送信する場合は、`BTS.MessageType` プロパティのフィルター処理を次の管理スキーマのいずれかに設定して、受信確認を取得します。  
  
  -   `http://schemas.microsoft.com/BizTalk/EDI/X12#X12_997_Root` (997 受信確認の場合)  
  
  -   `http://schemas.microsoft.com/BizTalk/EDI/X12#X12_TA1_Root` (TA1 受信確認の場合)  
  
  -   `http://schemas.microsoft.com/BizTalk/EDI/Efact#Efact_Contrl_Root` (CONTRL 受信確認の場合)  
  
- 非 EDI メッセージを送信する場合は、適切なフィルタを使用してメッセージを取得します。  
  
- AS2 メッセージを構築します。 このプロセスの詳細については、次を参照してください。[送信 AS2 メッセージを生成する](../core/generating-an-outgoing-as2-message.md)します。  
  
  > [!NOTE]
  >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、http、smtp、ftp などの URL の形式から、動的送信ポートで使用するトランスポートの種類を決定します。  
  
- メッセージや受信確認を送信ポートの送信先 URL にルーティングします。  
  
- メッセージや受信確認に対する MDN 応答を受信します (この処理が有効になっている送信請求応答の送信ポートの場合)。 このプロセスの詳細については、次を参照してください。[受信 MDN の処理](../core/processing-an-incoming-mdn.md)します。  
  
## <a name="see-also"></a>参照  
 [AS2 ソリューションのポートの構成](../core/configuring-ports-for-an-as2-solution.md)
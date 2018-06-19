---
title: AS2 経由でメッセージの静的送信ポートの構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2708d6a9-b105-42d3-abe3-7085b39da55a
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 068b7d8295710157af7a8a7358768e85e006beb8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969280"
---
# <a name="configuring-a-static-send-port-for-messages-over-as2"></a>AS2 経由でのメッセージの静的送信ポートの構成
このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成し、静的送信ポートを経由して AS2 メッセージを送信する方法について説明します。 この構成作業では、静的送信ポートを作成し、アグリーメントを構成します。 必要に応じて、送信ポートで使用される暗号化証明書のセットアップも行います。  
  
> [!NOTE]
>  静的送信ポートの代わりに、動的送信ポートを構成して AS2 メッセージを送信することもできます。 詳細については、次を参照してください。 [AS2 経由でメッセージの動的送信ポートを構成する](../core/configuring-a-dynamic-send-port-for-messages-over-as2.md)です。  
  
 EDI メッセージまたは非 EDI メッセージを持つ AS2 メッセージや EDI 受信確認を送信するには、次のように構成された送信請求 - 応答の HTTP 送信ポートを作成します。  
  
|場所|プロパティ|設定|  
|--------------|--------------|-------------|  
|**送信ポートのプロパティ: 全般**|ポートの種類|静的な送信請求-応答 (場合に mdn を要求する**受信確認 (Mdn)** 一方向アグリーメント タブのページが選択されている)<br /><br /> -静的な一方向の送信ポート (場合に mdn を要求する**受信確認 (Mdn)** 一方向アグリーメント タブのページではオフ)|  
|**送信ポートのプロパティ: 全般**|トランスポートの種類|HTTP<br /><br /> 注:<br /><br /> EDIINT/AS2 でエンコードされたメッセージには、HTTP アダプタのみ使用できます。 このトランスポートは、HTTP アダプタ以外のアダプタでは使用できません。|  
|**送信ポートのプロパティ: 全般**|送信ハンドラー|BizTalkServerApplication|  
|**送信ポートのプロパティ: 全般**|[送信パイプライン]|-AS2EdiSend (EDI でエンコードされたメッセージ)<br /><br /> -AS2Send (非 EDI メッセージの場合)|  
|**送信ポートのプロパティ: 全般**|[受信ハンドラー]<br /><br /> (場合に mdn を要求する**受信確認 (Mdn)** 一方向アグリーメント タブのページが選択されている)|BizTalkServerApplication|  
|**送信ポートのプロパティ: 全般**|受信パイプライン。<br /><br /> (場合に mdn を要求する**受信確認 (Mdn)** 一方向アグリーメント タブのページが選択されている)|AS2Receive|  
|**HTTP トランスポートのプロパティ**|送信先 URL|\<送信先 URL の文字列\>|  
|**HTTP トランスポートのプロパティ**|[チャンク エンコードを有効にする]|クリア|  
|**送信ポートのプロパティ: フィルター**|プロパティ|BTS.MessageType<br /><br /> 注:<br /><br /> BTS.ReceivePortName などの、さまざまなフィルタ式を使用できます。<br /><br /> 注:<br /><br /> 非 EDI メッセージの場合は、別のプロパティに対してフィルタ処理を行う必要があります。|  
|**送信ポートのプロパティ: フィルター**|演算子|==|  
|**送信ポートのプロパティ: フィルター**|値|- `http://schemas.microsoft.com/BizTalk/EDI/X12/2006#<schema name>`EDI メッセージ)<br /><br /> -                   `http://schemas.microsoft.com/Edi/X12#X12_<997 or TA1>_Root`(x12 受信確認)<br /><br /> -                   `http://schemas.microsoft.com/Edi/Efact#Efact_Contrl_Root`(EDIFACT 受信確認) を|  
|**送信ポートのプロパティ: 証明書**|"一般名" および "拇印"|送信 AS2 メッセージで暗号化証明書を使用する場合は、証明書の名前および拇印を入力します。|  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-biztalk-server-to-send-as2-messages-over-a-static-send-port"></a>静的送信ポート経由で AS2 メッセージを送信するように BizTalk Server を構成するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、前のように構成された、静的な一方向送信ポートまたは送信請求 - 応答の送信ポートを作成します。  
  
2.  送信ポートの一覧で、**送信ポート**の一方向アグリーメント タブのページ、**アグリーメントのプロパティ** ダイアログ ボックスで、静的な送信ポートの名前を入力します。  
  
    > [!NOTE]
    >  送信ポートを設定することにより、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は送信 AS2 メッセージのアグリーメントを解決できるようになります。  
  
3.  **識別子**の一方向アグリーメント タブのページ、**アグリーメントのプロパティ** ダイアログ ボックスで、AS2 の設定-変換先にプロパティの必要に応じてその他のアグリーメントのプロパティを設定し、さまざまなページ、**アグリーメントのプロパティ** ダイアログ ボックス。  
  
## <a name="functionality"></a>機能  
 静的送信ポートとパイプラインは、次の操作を実行し、AS2 経由で同期 EDI メッセージ、非 EDI メッセージ、または受信確認を送信し、返された MDN を処理します。  
  
-   EDI メッセージを送信する場合は、`BTS.MessageType` プロパティのフィルター処理を `http://schemas.microsoft.com/BizTalk/EDI/X12/2006` 名前空間のメッセージ スキーマに設定して (たとえば、864 メッセージの場合は X12_00401_864)、EDI メッセージを取得します。  
  
-   EDI 受信確認を送信する場合は、`BTS.MessageType` プロパティのフィルター処理を次の管理スキーマのいずれかに設定して、受信確認を取得します。  
  
    -   `http://schemas.microsoft.com/BizTalk/EDI/X12#X12_997_Root` (997 受信確認の場合)  
  
    -   `http://schemas.microsoft.com/BizTalk/EDI/X12#X12_TA1_Root` (TA1 受信確認の場合)  
  
    -   `http://schemas.microsoft.com/BizTalk/EDI/Efact#Efact_Contrl_Root` (CONTRL 受信確認の場合)  
  
-   非 EDI メッセージを送信する場合は、別のフィルタを使用してメッセージを取得します。  
  
-   AS2 メッセージを構築します。 このプロセスの詳細については、次を参照してください。[送信 AS2 メッセージを生成する](../core/generating-an-outgoing-as2-message.md)です。  
  
-   メッセージや受信確認を送信ポートの送信先 URL に送信します。  
  
-   メッセージや受信確認への MDN 応答を受信します (有効になっている場合)。 このプロセスの詳細については、次を参照してください。[着信 MDN の処理](../core/processing-an-incoming-mdn.md)です。  
  
## <a name="see-also"></a>参照  
 [AS2 ソリューションのポートを構成します。](../core/configuring-ports-for-an-as2-solution.md)   
 [送信 AS2 メッセージを生成します。](../core/generating-an-outgoing-as2-message.md)   
 [受信 MDN の処理](../core/processing-an-incoming-mdn.md)
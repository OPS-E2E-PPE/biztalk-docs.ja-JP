---
title: "JSON メッセージを処理するカスタム パイプラインを作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b04faad1-b14b-4146-82c7-88a38d2a46a5
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86c85f1a45dceb812fc805a66701653642d0ccb6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="create-custom-pipelines-to-process-json-messages"></a>JSON メッセージ処理用のカスタム パイプラインの作成
> [!NOTE]
>  このチュートリアルは、[!INCLUDE[prague](../includes/prague-md.md)] のみを対象としています。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリで JSON メッセージを処理する際に使用するパイプライン コンポーネントが提供されます。 この手順では、そのパイプラインを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリの構成時に使用するカスタム パイプラインを作成します。  
  
## <a name="create-a-custom-receive-pipeline"></a>カスタム受信パイプラインを作成します。  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューション エクスプ ローラーからのアプリケーションは、プロジェクトを右クリックし、順にポイント**追加** > **新しい項目の** > **受信パイプライン**. パイプラインの名前を付けて`JSONToXmlReceivePipeline.btp`、クリックして**追加**です。  
  
2.  内で、**デコード**ステージを追加、新しい**JSON デコーダー**です。 スクリーンショットのように、他のステージの他のパイプライン コンポーネントで変更を保存します。  
  
     ![カスタム受信パイプライン](../core/media/btsjson-receivepipeline.png "BTSJSON_ReceivePipeline")  
  
## <a name="create-a-custom-send-pipeline"></a>カスタム送信パイプラインを作成します。  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューション エクスプ ローラーからのアプリケーションは、プロジェクトを右クリックし、順にポイント**追加** > **新しい項目の** > **送信パイプライン**. パイプラインの名前を付けて`XmlToJSONSendPipeline.btp`、クリックして**追加**です。  
  
2.  内で、**エンコード**ステージを追加、新しい**JSON エンコーダー**です。 スクリーンショットのように、他のステージの他のパイプライン コンポーネントで変更を保存します。  
  
     ![カスタム送信パイプライン](../core/media/btsjson-sendpipeline.png "BTSJSON_SendPipeline")  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を使用して JSON メッセージの処理](../core/processing-json-messages-using-biztalk-server.md)
---
title: JSON メッセージを処理するカスタム パイプラインの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b04faad1-b14b-4146-82c7-88a38d2a46a5
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e28f825b1f26f3c080a02fd9a2e2bf8960a816fd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005995"
---
# <a name="create-custom-pipelines-to-process-json-messages"></a>JSON メッセージ処理用のカスタム パイプラインの作成
> [!NOTE]
>  このチュートリアルは、BizTalk Server にのみ適用されます。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリで JSON メッセージを処理する際に使用するパイプライン コンポーネントが提供されます。 この手順では、そのパイプラインを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリの構成時に使用するカスタム パイプラインを作成します。  
  
## <a name="create-a-custom-receive-pipeline"></a>カスタム受信パイプラインを作成します。  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューション エクスプ ローラーからのアプリケーション プロジェクトを右クリックし をポイント**追加** > **新しい項目の** > **受信パイプライン**. パイプラインの名前を付けて`JSONToXmlReceivePipeline.btp`、 をクリックし、**追加**します。  
  
2. 内で、**デコード**段階の新しい追加**JSON デコーダー**します。 スクリーンショットのように、他のステージの他のパイプライン コンポーネントで変更を保存します。  
  
    ![カスタム受信パイプライン](../core/media/btsjson-receivepipeline.png "BTSJSON_ReceivePipeline")  
  
## <a name="create-a-custom-send-pipeline"></a>カスタム送信パイプラインを作成します。  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューション エクスプ ローラーからのアプリケーション プロジェクトを右クリックし をポイント**追加** > **新しい項目の** > **送信パイプライン**. パイプラインの名前を付けて`XmlToJSONSendPipeline.btp`、 をクリックし、**追加**します。  
  
2. 内で、**エンコード**段階の新しい追加**JSON エンコーダー**します。 スクリーンショットのように、他のステージの他のパイプライン コンポーネントで変更を保存します。  
  
    ![カスタム送信パイプライン](../core/media/btsjson-sendpipeline.png "BTSJSON_SendPipeline")  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を使用して JSON メッセージの処理](../core/processing-json-messages-using-biztalk-server.md)
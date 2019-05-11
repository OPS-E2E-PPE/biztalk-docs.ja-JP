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
ms.openlocfilehash: 20b5600cfa54e5df6ae72c3a5f3bb03a255d4c08
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354278"
---
# <a name="create-custom-pipelines-to-process-json-messages"></a>JSON メッセージを処理するカスタム パイプラインを作成します。
> [!NOTE]
>  このチュートリアルは、BizTalk Server にのみ適用されます。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 内の JSON メッセージの処理に使用できるパイプライン コンポーネントを提供する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション。 この手順で使用してこれらのパイプライン コンポーネントを構成するときに使用できるカスタムのパイプラインを作成する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション。  
  
## <a name="create-a-custom-receive-pipeline"></a>カスタム受信パイプラインを作成します。  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューション エクスプ ローラーからのアプリケーション プロジェクトを右クリックし をポイント**追加** > **新しい項目の** > **受信パイプライン**. パイプラインの名前を付けて`JSONToXmlReceivePipeline.btp`、 をクリックし、**追加**します。  
  
2. 内で、**デコード**段階の新しい追加**JSON デコーダー**します。 その他のステージとその他のスクリーン ショットで示すように、パイプライン コンポーネントと変更を保存します。  
  
    ![カスタム受信パイプライン](../core/media/btsjson-receivepipeline.png "BTSJSON_ReceivePipeline")  
  
## <a name="create-a-custom-send-pipeline"></a>カスタム送信パイプラインを作成します。  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューション エクスプ ローラーからのアプリケーション プロジェクトを右クリックし をポイント**追加** > **新しい項目の** > **送信パイプライン**. パイプラインの名前を付けて`XmlToJSONSendPipeline.btp`、 をクリックし、**追加**します。  
  
2. 内で、**エンコード**段階の新しい追加**JSON エンコーダー**します。 その他のステージとその他のスクリーン ショットで示すように、パイプライン コンポーネントと変更を保存します。  
  
    ![カスタム送信パイプライン](../core/media/btsjson-sendpipeline.png "BTSJSON_SendPipeline")  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を使用して JSON メッセージの処理](../core/processing-json-messages-using-biztalk-server.md)
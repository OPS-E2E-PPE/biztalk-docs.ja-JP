---
title: インスタンス化し、送信アダプターの初期化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f10e6507-3351-4173-95f5-48546ca5f5c4
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3808af04a8b2bcf6f866629f254212d5b10b8d2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382077"
---
# <a name="instantiating-and-initializing-a-send-adapter"></a>送信アダプターのインスタンス化と初期化
既定では、送信アダプターは、最初のメッセージは「レイジー作成します」と呼ばれるプロセスには、配信されるまでインスタンス化されません。 既定のレイジー作成の方法は、システム リソースを節約するために役立ちます。 送信アダプターを作成した後がキャッシュされ、BizTalk Server サービスが停止されるまで有効にします。  
  
 **InitTransmitterOnServiceStart**のメンバー、**機能**列挙型の既定のレイジー作成を使用するのではなく、サービスの開始、送信アダプターを作成するメッセージング エンジンに指示これが必要な場合。  
  
 メッセージのバッチ処理に関するメッセージの受信を別のモデルは、メッセージを送信します。 受信の場合は、アダプターは、メッセージング エンジンから取得したバッチに挿入する受信メッセージが。 送信の場合は、メッセージング エンジンは、アダプターからバッチを取得し、送信アダプターにメッセージを送信します。 両方は、トランスポート プロキシを使用して、メッセージ バッチ オブジェクトを取得します。  
  
## <a name="how-a-send-adapter-is-initialized"></a>送信アダプターを初期化する方法  
 構成とバインディングを有効にする、トランスポート プロキシには、アダプターが次の構成インターフェイスを実装する必要があります。  
  
- **IBTTransport**  
  
- **IBaseComponent**  
  
- **IBTTransportControl**  
  
- **IPersistPropertyBag**  
  
  次の手順では、送信アダプターの初期化に関連するイベントのシーケンスについて説明します。  
  
1. まず実行、メッセージング エンジンでは、送信アダプターの初期化、 **QueryInterface**の**IPersistPropertyBag**、これは省略可能なインターフェイスです。 ハンドラーの構成がアダプターに渡されるアダプターは、インターフェイスを実装する場合、**ロード**メソッドの呼び出し。 アダプターでは、この情報を使用して、それが正しく構成されていることを確認します。  
  
2. メッセージング エンジンの実行、 **QueryInterface**の**IBTTransportControl**、必須インターフェイスであります。  
  
3. エンジンの呼び出し**IBTTransportControl.Initialize**アダプターのトランスポート プロキシに渡します。  
  
4. メッセージング エンジンの実行、 **QueryInterface**の**IBTTransmitter**します。  
  
    メッセージング エンジンにこのインターフェイスが検出された場合、アダプターはバッチ非対応の送信機として扱われます。  
  
    メッセージング エンジンが実行する場合は、メッセージング エンジンは、このインターフェイスを検出されず、 **QueryInterface**の**IBTBatchTransmitter**、検出するは、アダプターがバッチ対応であることを示します送信元。  
  
    これらのインターフェイスのどちらも、メッセージング エンジンが検出された場合、エラー状態となり、初期化に失敗します。 すべての必須インターフェイスが検出されない場合、初期化が失敗します。  
  
   次の図は、この API 呼び出しのシーケンスを示しています。青で示されるインターフェイスは、アダプターによって実装されます。  
  
   ![](../core/media/transmit-adapter-init.gif "Transmit_adapter_init")  
  
   アダプターは、それを初期化し、構成すると、すぐにメッセージを送信できます。  
  
   次の図は、送信アダプターの初期化に関連するオブジェクトの相互作用を示しています。  
  
   ![](../core/media/ebiz-sdk-devadapter10.gif "ebiz_sdk_devadapter10")  
   送信アダプターの初期化のワークフロー  
  
> [!NOTE]
>  アダプターがなど呼び出しにおいてメッセージング エンジンをブロックしないでください**IBTTransportControl.Initialize**と**IPersistPropertyBag.Load**します。 過度のこれらの呼び出しで処理を実行するサービスの開始時に影響を与えます。
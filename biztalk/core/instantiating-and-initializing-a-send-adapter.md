---
title: "インスタンス化して、送信アダプターの初期化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f10e6507-3351-4173-95f5-48546ca5f5c4
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07ed590b73d31a03a4b3316a4d84edfc1e39eb0f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="instantiating-and-initializing-a-send-adapter"></a>送信アダプターのインスタンス化と初期化
既定では、送信アダプターは、最初のメッセージが配信されるまでインスタンス化されません。これは "レイジー作成" と呼ばれるプロセスです。 レイジー作成による既定のアプローチは、システム リソースの節約に役立ちます。 作成された送信アダプターはキャッシュされ、BizTalk Server サービスが停止されるまで有効になります。  
  
 **InitTransmitterOnServiceStart**のメンバー、**機能**列挙型を既定のレイジー作成を使用するのではなく、サービスの開始に送信アダプターを作成するメッセージング エンジンに指示これが必要な場合です。  
  
 メッセージの送信は、メッセージのバッチ処理の点でメッセージの受信とは異なるモデルです。 受信の場合、アダプターには、メッセージング エンジンから取得したバッチに挿入する受信メッセージがあります。 送信の場合は、メッセージング エンジンがアダプターからバッチを取得し、送信先のアダプターにメッセージを送信します。 どちらの場合も、トランスポート プロキシを使用してメッセージ バッチ オブジェクトが取得されます。  
  
## <a name="how-a-send-adapter-is-initialized"></a>送信アダプターの初期化  
 構成およびトランスポート プロキシへのバインドを有効にするには、アダプターに次の構成インターフェイスを実装する必要があります。  
  
-   **IBTTransport**  
  
-   **IBaseComponent**  
  
-   **IBTTransportControl**  
  
-   **IPersistPropertyBag**  
  
 送信アダプターの初期化に関連する一連のイベントを次に示します。  
  
1.  まず実行、メッセージング エンジンには、送信アダプターが初期化されるときに、 **QueryInterface**の**IPersistPropertyBag**、これは省略可能なインターフェイスです。 ハンドラーの構成がアダプターに渡されるアダプターは、インターフェイスを実装する場合、**ロード**メソッドの呼び出しです。 アダプターは、この情報を使用して適切に構成されます。  
  
2.  メッセージング エンジンを実行、 **QueryInterface**の**IBTTransportControl**、これは必須のインターフェイスです。  
  
3.  エンジン呼び出し**IBTTransportControl.Initialize**アダプターのトランスポート プロキシに渡します。  
  
4.  メッセージング エンジンの実行、 **QueryInterface**の**IBTTransmitter**です。  
  
     このインターフェイスが検出された場合、アダプターはバッチ非対応の送信元として扱われます。  
  
     メッセージング エンジンを実行している場合は、メッセージング エンジンでは、このインターフェイスは検出しません、 **QueryInterface**の**IBTBatchTransmitter**、検出うちは、アダプターがバッチ対応であることを示します送信機能します。  
  
     これらのどちらのインターフェイスも検出されなかった場合、エラー状態となり、初期化が失敗します。 必須のインターフェイスのうち 1 つでも検出されないものがあると、初期化は失敗します。  
  
 この API の呼び出しの順序は、次の図のようになります。アダプターは、青色で示されるインターフェイスを実装します。  
  
 ![](../core/media/transmit-adapter-init.gif "Transmit_adapter_init")  
  
 アダプターは初期化して構成された時点で、すぐにメッセージを送信できるようになります。  
  
 送信アダプターを初期化するときの、オブジェクト間の対話処理を次に示します。  
  
 ![](../core/media/ebiz-sdk-devadapter10.gif "ebiz_sdk_devadapter10")  
送信アダプターの初期化のワークフロー  
  
> [!NOTE]
>  アダプターをブロックしないでください呼び出しにおいてメッセージング エンジンなど**IBTTransportControl.Initialize**と**IPersistPropertyBag.Load**です。 これらの呼び出しで過度な処理を実行した場合、サービスの開始が遅れる可能性があります。
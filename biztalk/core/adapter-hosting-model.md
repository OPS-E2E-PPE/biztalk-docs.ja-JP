---
title: "アダプターのホスト モデル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf9a8e6b-8c8d-47ec-b2a3-aed58206121d
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 645a1fcd41650c98c442549a898f7083be770842
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="adapter-hosting-model"></a>アダプターのホスト モデル
一般に BizTalk アダプターは BizTalk サービス Btsntsvc.exe でホストされます。 つまり、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アダプターの有効期間を管理します。 状況によっては、次に説明するように、他のプロセスがこのアダプターを管理する場合もあります。  
  
## <a name="in-process-adapters"></a>インプロセス アダプター  
 管理されているアダプター[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インプロセス アダプターと呼ばれます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]これらのアダプターは、次が行われます。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の起動時にアダプターをインスタンス化します。  
  
-   初期化時にアダプターのトランスポート プロキシをアダプターに渡します。  
  
-   アダプターの要求を処理します。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サービスのシャットダウン時にアダプターを終了します。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、実行時にハンドラー構成およびエンドポイント構成の情報をアダプターに送信します。 アダプターが要求をアクティブに処理できる特定の期間を定義するサービス時間帯などの、構成のその他の要素が指定されます。  
  
 BizTalk サービスが手動でシャット ダウンを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールまたはサービス コントロール マネージャーを使用しています。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースとの接続が失われた場合は、サービスが自動的に自身を再利用します。  
  
 一般的なホスト モデルでは、受信側アダプターと送信側アダプターが、メッセージング エンジンおよびオーケストレーション エンジンと共に、BizTalk サービスと同じプロセスでホストされます。 このホスト モデルでは、受信、送信、オーケストレーションの各ホストを柔軟に分離したり組み合わせたりすることができます。 次の図では、ホストが 3 つすべてを同じプロセスで実行しています。  
  
 多様なホスト モデルのため、アダプターを開発する際には、送信アダプターと受信アダプターを同じホストで構成できないことに留意する必要があります。 これらのアダプターは、別々のコンピューターで稼働するように構成される場合もあります。  
  
 ![](../core/media/regularadapterhostingmodel.gif "RegularAdapterHostingModel")  
インプロセス アダプターのホスト モデル  
  
## <a name="isolated-adapters"></a>分離アダプター  
 シナリオによっては、BizTalk サービスで受信アダプターをホストできない場合があります。 たとえば、インターネット インフォメーション サービス (IIS) のプロセス モデルでは、ASP.NET アプリケーションと ISAPI 拡張の有効期間が IIS で管理されるようになっています。 BizTalk SOAP アダプターは IIS と同じプロセス領域で実行する必要があるため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では SOAP アダプターのインスタンスの有効期間を制御できません。  
  
 これらのアダプターには、分離受信アダプター、または単に分離アダプターと呼ばれる別のホスト モデルが用意されています。 分離送信アダプターという概念は存在しません。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では分離アダプターを作成できないため、アダプターで独自のトランスポート プロキシを取得し、そのトランスポート プロキシでアダプターを登録する必要があります。  
  
 次の図は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のホスト アーキテクチャを示しています。 パフォーマンスを確保するために、分離ホスト アーキテクチャでは不要なプロセス間通信が削除されます。 分離アダプターと BizTalk メッセージング エンジン スタックは同じプロセスにあるため、アダプターでメッセージング エンジンが呼び出されているときはプロセス間通信は発生しません。 このシナリオでは、唯一のプロセス間通信は、メッセージング エンジンとデータベースの間で行われます。これは回避できません。  
  
 ![](../core/media/isolatedadapters.gif "IsolatedAdapters")  
分離アダプターのホスト モデル  
  
## <a name="see-also"></a>参照  
 [アダプター フレームワークとは何ですか。](../core/what-is-the-adapter-framework.md)
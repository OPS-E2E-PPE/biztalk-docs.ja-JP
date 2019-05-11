---
title: インターネットに接続する Web サービスと WCF サービスの発行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e7553608-f57a-470e-91d4-75504b3fd52b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c16812fc99c6fa38ad55c7e69afb8b6bb256136c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399550"
---
# <a name="publishing-internet-facing-web-services-and-wcf-services"></a>インターネットに接続する Web サービスと WCF サービスの発行
複数のアプローチを使用して、パブリッシング用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web サービスと WCF サービスをインターネット。  
  
- リバース プロキシ ルールを使用して、境界ネットワーク (DMZ、非武装地帯、およびスクリーン サブネットとも呼ばれます)。  
  
- 実行しているコンピュータ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]境界ネットワークのドメインに Web サービスまたは WCF サービスを発行します。  
  
- Azure AppFabric Service Bus のリレー エンドポイントとして、Web サービスまたは WCF サービスを公開するのに BizTalk Server のクラウドの有効化の機能を使用します。  
  
## <a name="using-a-reverse-proxy"></a>リバース プロキシを使用します。  
 これは、発行のため、従来のアプローチをされた[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web サービスと WCF サービス。 境界ネットワークでリバース プロキシ ルールを使用して、BizTalk サーバーを境界ネットワークにある必要があります。 リバース プロキシ ルール単に要求を転送、HTTP および SOAP、境界ネットワークから実行するコンピューターに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]イントラネット ドメインにします。  
  
 詳細については、リバース プロキシを使用して、BizTalk Server ヘルプで、次のトピックを参照してください。  
  
-   ["サンプル アーキテクチャ。HTTP アダプターと SOAP アダプター"](http://go.microsoft.com/fwlink/?LinkId=153339) (http://go.microsoft.com/fwlink/?LinkId=153339)します。  
  
-   ["サンプル TMA:HTTP アダプターと SOAP アダプター"](http://go.microsoft.com/fwlink/?LinkId=153340) (http://go.microsoft.com/fwlink/?LinkId=153340)します。  
  
-   ["大規模な分散アーキテクチャ"](http://go.microsoft.com/fwlink/?LinkId=153341) (http://go.microsoft.com/fwlink/?LinkId=153341)します。  
  
## <a name="using-computers-running-biztalk-server-in-the-perimeter-network"></a>境界ネットワーク内の BizTalk Server を実行しているコンピューターを使用します。  
 これは発行に対して推奨されるアプローチではありません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サービスまたはインターネットへの WCF サービスを実行しているコンピューターが必要とするため Web[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]境界ネットワーク内に配置します。 ただし、リバース プロキシが境界ネットワークで利用できない場合は、このアプローチを使用できます。  
  
 このアプローチには、イントラネット ドメインと一方向の信頼関係に参加する、境界ネットワークのドメインが必要があります (ただし、イントラネット ドメインでは、境界ネットワークのドメインを信頼しません)。 IIS アプリケーション ホストとなるプール、Web サービスまたは境界ネットワークのドメインでの WCF サービスは、「BizTalk 分離ホスト ユーザー」ドメインのグループ内にあるイントラネット ドメイン アカウントで実行する必要があります。 こうと、アプリケーション プールにメッセージを発行する必要な権限、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックス データベースです。  
  
 これに合わせてファイアウォールでは、特定のポートを開く必要があります。 必要なポートの詳細については、次を参照してください。 ["ポートを、受信と送信サーバー"](http://go.microsoft.com/fwlink/?LinkId=153342) (<http://go.microsoft.com/fwlink/?LinkId=153342>) で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ドキュメント。  
  
## <a name="exposing-biztalk-applications-on-the-cloud-using-appfabric-connect-for-services"></a>サービスの AppFabric Connect を使用して、クラウド上の BizTalk アプリケーションを公開します。  
 記事をご覧ください[サービスの AppFabric Connect を使用して、クラウドでの BizTalk アプリケーションの公開](http://go.microsoft.com/fwlink/?LinkID=204700)(http://go.microsoft.com/fwlink/?LinkID=204700)の詳細については、クラウドでの WCF サービスとしての BizTalk アプリケーションを公開します。  
  
## <a name="see-also"></a>参照  
 [Web Services1 を公開するための計画](../technical-guides/planning-for-publishing-web-services1.md)
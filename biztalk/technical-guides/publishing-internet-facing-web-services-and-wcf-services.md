---
title: "インターネットに接続された Web サービスと WCF サービスを発行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e7553608-f57a-470e-91d4-75504b3fd52b
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e466c4fc2a5f83f5a8445601235b53f44404a912
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="publishing-internet-facing-web-services-and-wcf-services"></a>インターネットに接続された Web サービスと WCF サービスの発行
複数の方法を使用するには発行のため[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web サービスと WCF サービスをインターネット。  
  
-   リバース プロキシ ルールを使用して、境界ネットワーク (DMZ、非武装地帯およびスクリーン サブネットとも呼ばれます)。  
  
-   実行するコンピューターに配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]境界ネットワークのドメインに、Web サービスまたは WCF サービスを発行します。  
  
-   Azure AppFabric Service Bus リレー エンドポイントとして、Web サービスまたは WCF サービスを公開するのにには、BizTalk Server クラウドの有効化の機能を使用します。  
  
## <a name="using-a-reverse-proxy"></a>リバース プロキシを使用します。  
 発行のための従来のアプローチがされてこの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web サービスと WCF サービスです。 リバース プロキシ ルールを使用して、境界ネットワーク内と、境界ネットワークにある BizTalk サーバーが存在する必要があります。 リバース プロキシ ルールだけで、HTTP および SOAP に要求を転送、境界ネットワークから実行しているコンピューター[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]イントラネット ドメインにします。  
  
 詳細については、リバース プロキシを使用して、BizTalk Server ヘルプの次のトピックを参照してください。  
  
-   ["サンプル アーキテクチャ: HTTP アダプタと SOAP アダプタ"](http://go.microsoft.com/fwlink/?LinkId=153339) (http://go.microsoft.com/fwlink/?LinkId=153339)。  
  
-   ["サンプル TMA: HTTP アダプタと SOAP アダプタ"](http://go.microsoft.com/fwlink/?LinkId=153340) (http://go.microsoft.com/fwlink/?LinkId=153340)。  
  
-   ["Large Distributed Architecture"](http://go.microsoft.com/fwlink/?LinkId=153341) (http://go.microsoft.com/fwlink/?LinkId=153341)。  
  
## <a name="using-computers-running-biztalk-server-in-the-perimeter-network"></a>境界ネットワークに BizTalk Server を実行しているコンピューターを使用します。  
 これは発行のため推奨できるアプローチではありません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web サービスまたはインターネットへの WCF サービスを実行しているコンピューターが必要とするため[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]境界ネットワーク内に配置します。 ただし、リバース プロキシを境界ネットワークで使用できない場合は、この方法を使用できます。  
  
 この方法には、イントラネット ドメインと一方向の信頼関係に参加する、境界ネットワークのドメインが必要があります (ただし、イントラネット ドメインは、境界ネットワークのドメインを信頼しません)。 IIS アプリケーション プールのホストは「BizTalk 分離ホスト ユーザー」のドメイン グループに属するイントラネット ドメイン アカウントでは、Web サービスや境界ネットワークのドメインでの WCF サービスを実行する必要があります。 こうと、アプリケーション プールにメッセージを公開する必要な権限、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックス データベースです。  
  
 これに合わせてファイアウォールで特定のポートを開く必要があります。 必要なポートの詳細については、次を参照してください。 ["ポート、受信と送信サーバーを"](http://go.microsoft.com/fwlink/?LinkId=153342) (http://go.microsoft.com/fwlink/?LinkId=153342) で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ドキュメント。  
  
## <a name="exposing-biztalk-applications-on-the-cloud-using-appfabric-connect-for-services"></a>AppFabric Connect サービスを使用するクラウド上の BizTalk アプリケーションを公開します。  
 記事を参照して[AppFabric Connect サービスを使用するクラウドに BizTalk アプリケーションを公開する](http://go.microsoft.com/fwlink/?LinkID=204700)(http://go.microsoft.com/fwlink/?LinkID=204700) の詳細については、クラウドでの WCF サービスとしての BizTalk アプリケーションを公開します。  
  
## <a name="see-also"></a>参照  
 [Web Services1 を公開するための計画](../technical-guides/planning-for-publishing-web-services1.md)
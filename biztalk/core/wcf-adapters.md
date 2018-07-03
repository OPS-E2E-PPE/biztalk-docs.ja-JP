---
title: WCF アダプター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e64cd189-8805-4209-bd06-971363f38585
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c4980eb1045d12986ec486308231ab2f219445b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993811"
---
# <a name="wcf-adapters"></a>WCF アダプタ

## <a name="overview"></a>概要
Windows Communication Foundation (WCF) 向け BizTalk アダプターを使用すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で WCF ベースのアプリケーションと通信できます。 BizTalk WCF アダプタには、WCF 定義済みバインドを表す 5 つの物理アダプタが含まれています —**BasicHttpBinding**、 **WsHttpBinding**、 **NetTcpBinding**、 **NetNamedPipeBinding**、および**NetMsmqBinding**します。 定義済みバインド用 WCF アダプタの目的は、大半のアプリケーション要件に必要な情報の構成を合理化することです。  
  
 BizTalk WCF アダプタには、受信場所と送信ポートに関する WCF バインドと動作情報を自由に構成するために使用される、2 つのアダプタも含まれています。  

## <a name="available-wcf-adapters"></a>使用可能な WCF アダプター
    
- **Wcf-wshttp アダプター**します。 HTTP トランスポート経由の WS-* 標準をサポートします。 WCF-WSHttp アダプターは、外部アプリケーションと MessageBox データベース間のトランザクション上の対話に WS-Transaction、メッセージ セキュリティと認証に WS-Security という仕様を実装します。 トランスポートは HTTP または HTTPS で、メッセージのエンコードは、テキスト エンコードまたは Message Transmission Optimization Mechanism (MTOM) エンコードです。  
  
- **Wcf-basichttp アダプター**します。 ASMX ベースの Web サービスとクライアント、および WS-I Basic Profile 1.1 に準拠する他のサービスと通信します。 トランスポートは HTTP または HTTPS で、メッセージ エンコードは Text エンコードです。  
  
- **Wcf-nettcp アダプター**します。 TCP トランスポート経由の WS-* 標準をサポートします。 WCF-NetTcp アダプタは、WCF-to-WCF 環境での効率的な通信を提供します。 アダプターは、次の仕様を実装: 外部アプリケーションとメッセージ ボックス データベースでは、Ws-security とメッセージ セキュリティと認証用のトランザクション対話の WS トランザクション。 トランスポートは TCP で、メッセージのエンコードはバイナリ エンコードです。  
  
- **Wcf-netmsmq アダプター**します。 [!INCLUDE[btsCoName](../includes/btsconame-md.md)] メッセージ キュー (MSMQ) をトランスポートとして利用することにより、キューをサポートします。疎結合アプリケーションのサポート、エラーの分離、負荷の平準化、および切断時の操作を可能にします。  
  
- **Wcf-netnamedpipe アダプター**します。 コンピューター上のプロセス間通信をセキュリティで保護された状態で最適化します。 WCF-NetNamedPipe アダプターはトランスポート セキュリティを使用して、転送時のセキュリティ、メッセージ配信の名前付きパイプ、メッセージのバイナリ エンコードを実現します。  
  
- **WCF カスタム アダプター**します。 WCF 拡張機能を使用できるようにします。 アダプタでは、受信場所および送信ポートに対して、ユーザーが WCF のバインドおよび動作情報を選択し、構成できます。  
  
- **Wcf-customisolated アダプター**します。 HTTP トランスポート経由で WCF 拡張機能を使用できるようにします。 このアダプタでは、分離ホストで実行している受信場所に対して、WCF バインドと WCF 動作情報を選択および構成できます。  
  
  さらに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には BizTalk WCF サービス公開ウィザードと BizTalk WCF サービス使用ウィザードが用意されています。 BizTalk Web サービス公開ウィザードを使用すると、BizTalk オーケストレーションを WCF サービスとして作成および公開したり、スキーマを WCF サービスとして公開したりすることができます。 BizTalk WCF サービス使用ウィザードでは、オーケストレーションや種類など、WCF サービスのメタデータ ドキュメントに基づいて WCF サービスを使用するための [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アイテムを生成します。  
  
  このセクションでは、WCF アダプタを構成して展開するのに役立つリソースを紹介します。  
  
## <a name="next"></a>Next 
  
-   [WCF アダプターについて](../core/what-are-the-wcf-adapters.md)  
  
-   [WCF アダプターの構成](../core/configuring-the-wcf-adapters.md)  
  
-   [WCF-BasicHttp アダプター](../core/wcf-basichttp-adapter.md)  
  
-   [WCF-WSHttp アダプター](../core/wcf-wshttp-adapter.md)  
  
-   [WCF-NetTcp アダプター](../core/wcf-nettcp-adapter.md)  
  
-   [WCF-NetMsmq アダプター](../core/wcf-netmsmq-adapter.md)  
  
-   [WCF-NetNamedPipe アダプター](../core/wcf-netnamedpipe-adapter.md)  
  
-   [WCF-Custom アダプター](../core/wcf-custom-adapter.md)  
  
-   [WCF-CustomIsolated アダプター](../core/wcf-customisolated-adapter.md)  
  
## <a name="see-also"></a>参照  
 [WCF サービスの使用](../core/using-wcf-services.md)   
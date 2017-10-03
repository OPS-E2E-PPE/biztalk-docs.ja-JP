---
title: "WCF アダプタ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e64cd189-8805-4209-bd06-971363f38585
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb77124dbad631cd521a285ff4f036e0545ca819
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="wcf-adapters"></a>WCF アダプタ

## <a name="overview"></a>概要
Windows Communication Foundation (WCF) 向け BizTalk アダプターを使用すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で WCF ベースのアプリケーションと通信できます。 BizTalk WCF アダプターは、WCF 定義済みバインドを表す 5 つの物理アダプターを含める-**BasicHttpBinding**、 **WsHttpBinding**、 **NetTcpBinding**、 **NetNamedPipeBinding**、および**NetMsmqBinding**です。 定義済みバインド用 WCF アダプタの目的は、大半のアプリケーション要件に必要な情報の構成を合理化することです。  
  
 BizTalk WCF アダプタには、受信場所と送信ポートに関する WCF バインドと動作情報を自由に構成するために使用される、2 つのアダプタも含まれています。  

## <a name="available-wcf-adapters"></a>使用可能な WCF アダプター
    
-   **Wcf-wshttp アダプタ**です。 HTTP トランスポート経由の WS-* 標準をサポートします。 WCF-WSHttp アダプターは、外部アプリケーションと MessageBox データベース間のトランザクション上の対話に WS-Transaction、メッセージ セキュリティと認証に WS-Security という仕様を実装します。 トランスポートは HTTP または HTTPS で、メッセージのエンコードは、テキスト エンコードまたは Message Transmission Optimization Mechanism (MTOM) エンコードです。  
  
-   **Wcf-basichttp アダプター**です。 ASMX ベースの Web サービスとクライアント、および WS-I Basic Profile 1.1 に準拠する他のサービスと通信します。 トランスポートは HTTP または HTTPS で、メッセージ エンコードは Text エンコードです。  
  
-   **Wcf-nettcp アダプター**です。 TCP トランスポート経由の WS-* 標準をサポートします。 WCF-NetTcp アダプタは、WCF-to-WCF 環境での効率的な通信を提供します。 アダプターは、次の仕様を実装して: 外部アプリケーションとメッセージ ボックス データベース、および Ws-security 間は、メッセージ セキュリティと認証の間のやり取りをトランザクションの WS トランザクションです。 トランスポートは TCP で、メッセージのエンコードはバイナリ エンコードです。  
  
-   **Wcf-netmsmq アダプタ**です。 [!INCLUDE[btsCoName](../includes/btsconame-md.md)] メッセージ キュー (MSMQ) をトランスポートとして利用することにより、キューをサポートします。疎結合アプリケーションのサポート、エラーの分離、負荷の平準化、および切断時の操作を可能にします。  
  
-   **Wcf-netnamedpipe アダプタ**です。 コンピューター上のプロセス間通信をセキュリティで保護された状態で最適化します。 WCF-NetNamedPipe アダプターはトランスポート セキュリティを使用して、転送時のセキュリティ、メッセージ配信の名前付きパイプ、メッセージのバイナリ エンコードを実現します。  
  
-   **WCF カスタム アダプター**です。 WCF 拡張機能を使用できるようにします。 アダプタでは、受信場所および送信ポートに対して、ユーザーが WCF のバインドおよび動作情報を選択し、構成できます。  
  
-   **Wcf-customisolated アダプター**です。 HTTP トランスポート経由で WCF 拡張機能を使用できるようにします。 このアダプタでは、分離ホストで実行している受信場所に対して、WCF バインドと WCF 動作情報を選択および構成できます。  
  
 さらに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には BizTalk WCF サービス公開ウィザードと BizTalk WCF サービス使用ウィザードが用意されています。 BizTalk Web サービス公開ウィザードを使用すると、BizTalk オーケストレーションを WCF サービスとして作成および公開したり、スキーマを WCF サービスとして公開したりすることができます。 BizTalk WCF サービス使用ウィザードでは、オーケストレーションや種類など、WCF サービスのメタデータ ドキュメントに基づいて WCF サービスを使用するための [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アイテムを生成します。  
  
 このセクションでは、WCF アダプタを構成して展開するのに役立つリソースを紹介します。  
  
## <a name="next"></a>Next 
  
-   [WCF アダプタは?](../core/what-are-the-wcf-adapters.md)  
  
-   [WCF アダプタの構成](../core/configuring-the-wcf-adapters.md)  
  
-   [WCF-BasicHttp アダプター](../core/wcf-basichttp-adapter.md)  
  
-   [Wcf-wshttp アダプター](../core/wcf-wshttp-adapter.md)  
  
-   [Wcf-nettcp アダプター](../core/wcf-nettcp-adapter.md)  
  
-   [Wcf-netmsmq アダプター](../core/wcf-netmsmq-adapter.md)  
  
-   [Wcf-netnamedpipe アダプター](../core/wcf-netnamedpipe-adapter.md)  
  
-   [Wcf-custom アダプター](../core/wcf-custom-adapter.md)  
  
-   [Wcf-customisolated アダプター](../core/wcf-customisolated-adapter.md)  
  
## <a name="see-also"></a>参照  
 [WCF サービスの使用](../core/using-wcf-services.md)   
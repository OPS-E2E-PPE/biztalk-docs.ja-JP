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
ms.openlocfilehash: 716154cbc315c24f7a6a3cd65f9d26a7dfe2fa54
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399419"
---
# <a name="wcf-adapters"></a>WCF アダプタ

## <a name="overview"></a>概要
BizTalk アダプターの Windows Communication Foundation (WCF) を許可する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]WCF ベースのアプリケーションと通信します。 BizTalk WCF アダプタには、WCF 定義済みバインドを表す 5 つの物理アダプタが含まれています —**BasicHttpBinding**、 **WsHttpBinding**、 **NetTcpBinding**、 **NetNamedPipeBinding**、および**NetMsmqBinding**します。 定義済みバインド用 WCF アダプタは、ほとんどのアプリケーション要件に必要な情報を簡単に構成するために提供されます。  
  
 BizTalk WCF アダプターでは、WCF バインドと動作については、受信場所の構成し、送信ポートを自由にするための 2 つのアダプターも含まれます。  

## <a name="available-wcf-adapters"></a>使用可能な WCF アダプター
    
- **Wcf-wshttp アダプター**します。 Ws-* 標準 HTTP トランスポート経由でサポートされています。 Wcf-wshttp アダプタは、次の仕様を実装します。WS トランザクションの外部アプリケーションとメッセージ ボックス データベースでは、Ws-security とは、メッセージ セキュリティと認証のトランザクション対話を処理します。 トランスポートは HTTP または HTTPS、およびメッセージのエンコードは、テキストまたは Message Transmission Optimization Mechanism (MTOM) エンコードします。  
  
- **Wcf-basichttp アダプター**します。 ASMX ベースの Web サービスとクライアント、および、WS に準拠するその他のサービスと通信の基本プロファイル 1.1。 トランスポートは HTTP または HTTPS、およびメッセージのエンコードは text エンコードです。  
  
- **Wcf-nettcp アダプター**します。 Ws-* 標準 TCP トランスポート経由でサポートされています。 Wcf-nettcp アダプターは、WCF の環境での効率的な通信を提供します。 アダプターは、次の仕様を実装します。WS トランザクションの外部アプリケーションとメッセージ ボックス データベースでは、Ws-security とは、メッセージ セキュリティと認証のトランザクション対話を処理します。 トランスポートは TCP、およびメッセージのエンコードはバイナリ エンコードです。  
  
- **Wcf-netmsmq アダプター**します。 使用したキューのサポートを提供します。[!INCLUDE[btsCoName](../includes/btsconame-md.md)]メッセージ キュー (MSMQ) トランスポートと有効が疎結合アプリケーション、エラーの分離のサポートとして負荷平準化、および切断操作。  
  
- **Wcf-netnamedpipe アダプター**します。 セキュリティで保護されたコンピューター上のプロセス間通信の最適化を提供します。 Wcf-netnamedpipe アダプタは、メッセージの配信、およびバイナリ メッセージ エンコーディングの名前付きパイプ、転送セキュリティ用トランスポート セキュリティを使用します。  
  
- **WCF カスタム アダプター**します。 WCF の拡張機能を使用できるようにします。 アダプターを使用すると、WCF バインドと動作については、受信場所の構成および送信ポートを選択できます。  
  
- **Wcf-customisolated アダプター**します。 HTTP トランスポート経由で WCF 拡張機能を使用できるようにします。 アダプターを選択し、WCF バインドと、分離ホストで実行されている受信場所の動作情報を構成することができます。  
  
  さらに、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] BizTalk WCF サービス公開ウィザードと BizTalk WCF サービス使用ウィザードを提供します。 作成し、BizTalk オーケストレーションを WCF サービスとして公開して、スキーマを WCF サービスとして公開するには、BizTalk WCF サービス公開ウィザードを使用することができます。 BizTalk WCF サービス使用ウィザードを使用して、生成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]WCF サービスのメタデータ ドキュメントに基づいてオーケストレーションや種類、WCF サービスを使用するなど、成果物。  
  
  このセクションでは、構成、および WCF アダプタの展開に役立つリソースを提供します。  
  
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
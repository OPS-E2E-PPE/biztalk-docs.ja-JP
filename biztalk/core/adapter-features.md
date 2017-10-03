---
title: "アダプターの機能 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TIBCO Enterprise adapters, message delivery
- architecture, TIBCO Enterprise adapters
- TIBCO Enterprise adapters, architecture
- TIBCO Enterprise adapters, data validation
ms.assetid: ede748ce-3f28-4942-b2bd-e38e5f1b0f54
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ffa789837973f8c8c7bb6c5bd428e36c562df96c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="adapter-features"></a>アダプタの機能
Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) により、BizTalk Server と TIBCO SDK を使用して、TIBCO EMS によって管理されているキューおよびトピックに対して公開とサブスクライブを行うことができます。 このアダプターは、TIBCO EMS メッセージを迅速で簡単に、信頼できる方法で統合します。 TIBCO EMS サービスと Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 間で XML データ形式を交換することで、密接に統合された信頼性の高いアプリケーション インフラストラクチャが構築されます。 送信用と受信用のアダプター統合操作により、XML スキーマを使用したエンドツーエンドのビジネス プロセス管理が提供されます。  
  
## <a name="data-validation"></a>データの検証  
 BizTalk Adapter for TIBCO EMS は、密接に統合されたネイティブ アダプターとして BizTalk Server ホストとインプロセスで実行され、構成時にポート構成を検証します。 有効な名前、有効な番号、有効な範囲など、最大限のデータが検証されます。 接続は試行されません。 そのため、ホスト、ポート送信先、ユーザー、およびパスワードは、実行時に呼び出されるまで検証されず、その時点でエラーが記録されます。  
  
## <a name="message-delivery"></a>メッセージ配信  
 BizTalk Adapter for TIBCO EMS は、メッセージの 1 回限りの配信を保証します。 EMS に到達しないメッセージは、中断時に再試行可能としてマークされます。 これには、いくつかの例外があります。たとえば、実行時に無効なポート構成が存在する場合などです。  
  
 アダプターは、テキスト EMS メッセージの種類を受け入れます。  アダプターは、EMS への送信メッセージのトランザクションをサポートし、トランザクションのサポートはによって制御されます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。  
  
> [!NOTE]
>  BizTalk Adapter for TIBCO EMS と EMS サーバー間の接続は、セキュリティで保護されません。 セキュリティは、提供された TIBCO EMS SDK でサポートされていません。  
  
 このアダプターは、すべての標準 JMS プロパティと EMS 拡張機能をサポートします。 これらのプロパティは、オーケストレーションで使用できるように BizTalk メッセージのコンテキストに配置されます。  
  
## <a name="general-adapter-features"></a>全般的なアダプターの機能  
 BizTalk Adapter for TIBCO EMS は、TIBCO EMS システムと BizTalk Server 間で、ビジネス データをリアルタイムで交換する手段を提供します。 このアダプターにより、XML アプリケーションと TIBCO EMS 間の対話が可能になります。 TIBCO EMS で、XML アプリケーションの受信および送信の処理を実行できます。  
  
 アダプターは、次のいずれかの方法で、BizTalk Server アプリケーションと TIBCO EMS 間の通信を可能にする XML メッセージを受け入れます。  
  
-   静的な一方向の送信ポートを使用して、TIBCO EMS にメッセージを送信するアダプターを送信します。  
  
-   受信アダプター: 静的な一方向受信ポートを使用して、TIBCO EMS からメッセージを受信します。  
  
### <a name="transmit-adapter-architecture-send--static-one-way"></a>送信アダプターのアーキテクチャ: 送信-静的な一方向  
 一方向送信の場合、メッセージがキューまたはトピックに送信されるように送信ポートを構成します。 BizTalk Adapter for TIBCO Enterprise Message Service は、指定されたキューまたはトピックに、TIBCO EMS サーバーへの要求を転送します。 TIBCO EMS システムへのメッセージの送信には、TIBCO EMS 通信プロトコルが使用されます。 TIBCO EMS システムは、要求を受信して、ビジネス ロジックを実行します。 TIBCO EMS への呼び出しを作成するには、TIBCO EMS サーバーにアクセスするための構成情報をアダプターに提供する必要があります。  
  
 次の図に、このアダプターの一方向送信操作を示します。  
  
 ![](../core/media/tibcoems-architecture-send.gif "TIBCOEMS_architecture_send")  
  
### <a name="receive-adapter-architecture-receive--static-one-way"></a>静的な一方向: 受信アダプターのアーキテクチャが表示されます。  
 一方向受信の場合、EMS キューまたはトピックのメッセージを受信するように受信場所を構成します。 BizTalk Adapter for TIBCO EMS は、指定されたキューまたはトピックのメッセージを待ち受け、受信したメッセージを BizTalk Server に送信します。  
  
 次の図に、このアダプターの一方向受信操作を示します。  
  
 ![](../core/media/tibcoems-architecture-receive.gif "TIBCOEMS_architecture_receive")  
  
## <a name="see-also"></a>参照  
 [アプリケーションの開発](../core/developing-applications5.md)   
 [作業の開始](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)
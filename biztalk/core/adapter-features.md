---
title: TIBCO Enterprise Message Service アダプターの機能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ede748ce-3f28-4942-b2bd-e38e5f1b0f54
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d923f439598f9eaa924924b6c7a628caf62d32e9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361556"
---
# <a name="tibco-ems-adapter-features"></a>TIBCO EMS アダプターの機能
Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) を使用すると、キューおよび BizTalk Server と TIBCO SDK を使用して、TIBCO EMS によって管理されているトピックにパブリッシュおよびサブスクライブできます。 アダプターは、TIBCO EMS メッセージを高速かつ信頼性の高い方法で統合します。 TIBCO EMS サーバーと Microsoft 間の XML データ形式を交換[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]緊密に統合され信頼性の高いアプリケーション インフラストラクチャを提供します。 送信と受信アダプター統合操作の XML スキーマを使用してエンド ツー エンドのビジネス プロセス管理を提供します。  
  
## <a name="data-validation"></a>データの検証  
 BizTalk Adapter for TIBCO EMS でインプロセスで動作として、ネイティブでは、BizTalk Server ホストでは密接にアダプターを統合し、構成時にポートの構成を検証します。 データ可能な限り - たとえば、有効な名前、有効な番号、有効範囲を検証します。 接続を作成するのには行いません。 そのため、ホスト、ポート送信先、ユーザー、およびパスワードは検証されない場合にエラーが記録されます、実行時の呼び出しがあるまで。  
  
## <a name="message-delivery"></a>メッセージ配信  
 BizTalk Adapter for TIBCO EMS は、メッセージのうちの 1 回限りの配信を保証します。 EMS に到達しないメッセージは、中断時に再試行可能としてマークされます。 あります、これをいくつかの例外などの実行時に、無効なポートの構成が存在する場合。  
  
 アダプターは、テキスト EMS メッセージの種類を受け入れます。  アダプターは、EMS への送信メッセージのトランザクションをサポートしているし、トランザクションのサポートはによって制御されます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
> [!NOTE]
>  BizTalk Adapter for TIBCO EMS と EMS サーバー間の接続は安全ではありません。 指定された TIBCO EMS SDK ではサポートされません。  
  
 アダプターは、すべての標準 JMS プロパティと EMS 拡張機能をサポートします。 これらのプロパティは、オーケストレーションに使用する BizTalk メッセージ コンテキストに格納されます。  
  
## <a name="general-adapter-features"></a>[全般] アダプターの機能  
 BizTalk Adapter for TIBCO EMS は、TIBCO EMS システムと BizTalk Server の間のリアルタイムのビジネス データを交換する手段を提供します。 アダプタでは、XML アプリケーションと TIBCO EMS 間の対話できます。 TIBCO EMS で受信および送信の処理のための XML アプリケーションに有効にするとします。  
  
 アダプターは、次のいずれかを使用して TIBCO EMS と通信するために BizTalk Server アプリケーションを有効にする XML メッセージを受け取ります。  
  
-   送信アダプター、静的な一方向の送信ポートを使用して、TIBCO EMS にメッセージを送信します。  
  
-   受信アダプターは、静的な一方向の受信ポートを使用して、TIBCO EMS からメッセージを受信します。  
  
### <a name="transmit-adapter-architecture-send--static-one-way"></a>送信アダプターのアーキテクチャ。送信-静的な一方向  
 一方向の送信では、キュー/トピックにメッセージを送信する送信ポートが構成されています。 BizTalk Adapter for TIBCO Enterprise Message Service は、指定されたキューまたはトピックに TIBCO EMS サーバーへの要求を転送します。 アダプターは、TIBCO EMS 通信プロトコルを使用して、TIBCO EMS システムにメッセージを送信します。 TIBCO EMS システムは、要求を受信し、ビジネス ロジックを実行します。 TIBCO EMS への呼び出しをするためには、TIBCO EMS サーバーへのアクセスの構成情報をアダプターに提供する必要があります。  
  
 次の図は、アダプターの一方向の送信操作を示します。  
  
 ![](../core/media/tibcoems-architecture-send.gif "TIBCOEMS_architecture_send")  
  
### <a name="receive-adapter-architecture-receive--static-one-way"></a>受信アダプターのアーキテクチャ。受信-静的な一方向  
 一方向の受信シナリオでは、EMS キューまたはトピック メッセージを受信する受信場所を構成します。 BizTalk Adapter for TIBCO EMS は、指定されたキューまたはトピックにメッセージをリッスンし、BizTalk Server に受信したメッセージを送信します。  
  
 次の図は、このアダプターの一方向の受信操作。  
  
 ![](../core/media/tibcoems-architecture-receive.gif "TIBCOEMS_architecture_receive")  
  
## <a name="see-also"></a>参照  
 [アプリケーションの開発](../core/developing-applications5.md)   
 [作業の開始](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)
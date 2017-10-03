---
title: "SAP アダプターのサンプル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- samples, Data Provider for SAP
- samples, migration
- samples, BizTalk
- samples, WCF service model
- samples, WCF channel model
- samples
ms.assetid: 4654c458-83be-417f-ae54-5c3a8f6ab81f
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0374aada037282a68e7575136b8671bba5ca181d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="samples-for-the-sap-adapter"></a>SAP アダプターのサンプル
サンプルを[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]に分類されます。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]サンプル  
  
-   WCF サービス モデルのサンプル  
  
-   WCF チャネル モデルのサンプル  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]サンプル  
  
-   移行のサンプル  
  
 サンプルはいただけます[http://go.microsoft.com/fwlink/?LinkID=196854](http://go.microsoft.com/fwlink/?LinkID=196854)です。  
  
 次の一覧には、名前と、サンプルの説明が含まれています、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
## <a name="biztalk-server-samples"></a>BizTalk Server のサンプル  
  
|サンプルのディレクトリ名|Description|  
|---------------------------|-----------------|  
|IDOCSend|IDOC を SAP システムに送信する方法を示します。|  
|ReceiveIDOC|SAP システムから IDOC を受信する方法を示します。|  
|ReceiveIDOC_SYSREL|SAP システムから IDOC を受信する方法を示します。 IDOC の受信中には、SAP SYSREL 未満のバージョン番号があります。|  
|RFCServer|SAP システムから RFC サーバー呼び出しを受信する方法を示します。|  
|SAPTransaction|使用して SAP システムでトランザクションを実行する方法を示します。|  
|tRFCClient|SAP システムで tRFC クライアント呼び出しを行う方法を示します。|  
  
## <a name="wcf-service-model-samples"></a>WCF サービス モデルのサンプル  
  
|サンプルのディレクトリ名|Description|  
|---------------------------|-----------------|  
|SapIdocStringClientSM|SendIdoc 操作を呼び出すことによって、IDOC を SAP システムに送信する方法を示します。|  
|SapRfcServerSM|SAP システムから RFC サーバー呼び出しを受信する方法を示します。|  
|SapBapiTxClientSM|SAP システムでトランザクション内の Bapi を呼び出す方法を示します。|  
|SapTrfcClientSM|SAP システムで tRFC クライアント呼び出しを起動する方法を示します。|  
  
## <a name="wcf-channel-model-samples"></a>WCF チャネル モデルのサンプル  
  
|サンプルのディレクトリ名|Description|  
|---------------------------|-----------------|  
|SapIdocReceiveCM|SAP システムから Idoc を受信する方法を示します|  
|SapRfcServerCM|SAP システムから RFC サーバー呼び出しを受信する方法を示します。|  
  
## <a name="data-provider-for-sap-samples"></a>Data Provider for SAP のサンプル  
  
|サンプルのディレクトリ名|Description|  
|---------------------------|-----------------|  
|sap ado|使用する方法を示します、[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]です。|  
  
## <a name="migration-samples"></a>移行のサンプル  
  
|サンプルのディレクトリ名|Description|  
|---------------------------|-----------------|  
|SAP_RFC_Migration|SAP アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトを使用して、WCF ベースで利用する方法を示します[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 BizTalk プロジェクトには、SD_RFC_CUSTOMER_GET RFC を呼び出すオーケストレーションが含まれています。|  
|SendIDOC_Migration|SAP アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトを使用して、WCF ベースで利用する方法を示します[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 BizTalk プロジェクトには、IDOC を SAP システムに送信するオーケストレーションが含まれています。|  
|ReceiveIDOC_Migration|SAP アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトを使用して、WCF ベースで利用する方法を示します[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 BizTalk プロジェクトには、SAP システムから IDOC の受信を呼び出すオーケストレーションが含まれています。|  
  
## <a name="see-also"></a>参照  
[SAP アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)
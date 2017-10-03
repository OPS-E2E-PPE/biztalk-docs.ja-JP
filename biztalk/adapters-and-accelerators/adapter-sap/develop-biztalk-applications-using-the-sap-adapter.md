---
title: "SAP アダプターを使用して BizTalk アプリケーションを開発 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk applications, developing
- developing, BizTalk applications
ms.assetid: 4aa10897-a08e-4fc3-9c1f-40485d204273
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75e70a52f12227b1bde3a43f9330c6fe373ac5a3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="develop-biztalk-applications-using-the-sap-adapter"></a>SAP アダプターを使用して BizTalk アプリケーションを開発します。
BizTalk アプリケーションの開発で BizTalk プロジェクトを作成する[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用して、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]XML スキーマを生成します。 スキーマが生成されると、コンテンツ ベースのルーティング (CBR) を使用するか、生成されたスキーマに準拠するメッセージを送受信する BizTalk オーケストレーションを作成します。  
  
 CBR は、ここで、SAP システムに送信されるメッセージには、処理を要する処理は不要のシナリオで使用できます。 たとえば、受信ポートが特定の型だけのメッセージを受信することがわかっている場合は、送信ポートにフィルター式と一致するメッセージをルーティングする送信ポートにフィルターを追加できます。  
  
 、BizTalk オーケストレーションの送信を作成およびとの間でメッセージを送受信する受信ポート、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、さらに、メッセージを送信する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 このセクションでは、BizTalk オーケストレーションを使用して SAP システムを使用して、操作を実行するに関する情報を提供、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]順番に使用して、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)] WCF バインドと対話できるアダプター。  
  
> [!IMPORTANT]
>  使用する、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、常に設定する必要があります、 **EnableBizTalkCompatibilityMode**にプロパティのバインド**True**です。 バインドのプロパティを設定する方法については、次を参照してください。 [SAP アダプターのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SAP アプリケーションを作成するための必要条件](../../adapters-and-accelerators/adapter-sap/prerequisites-to-create-sap-applications.md)
  
-   [SAP アプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)
  
-   [BizTalk Server を使用して SAP Rfc を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md)  
  
-   [BizTalk Server を使用して SAP から受信 RFC 呼び出しの受信します。](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-from-sap-using-biztalk-server.md)  
  
-   [BizTalk Server を使用して SAP で tRFCs を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-biztalk-server.md)  
  
-   [BizTalk Server を使用して SAP から受信 tRFC の呼び出しを受信します。](../../adapters-and-accelerators/adapter-sap/receive-inbound-trfc-calls-from-sap-using-biztalk-server.md)  
  
-   [BizTalk Server を使用して SAP でトランザクションを BAPI を実行します。](../../adapters-and-accelerators/adapter-sap/run-bapi-transactions-in-sap-using-biztalk-server.md)  
  
-   [BizTalk Server を使用して sap Idoc を送信します。](../../adapters-and-accelerators/adapter-sap/send-idocs-to-sap-using-biztalk-server.md)  
  
-   [BizTalk Server を使用して SAP からの Idoc を受信します。](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-using-biztalk-server.md)  
  
-   [BizTalk Server を使用して、トランザクションのコンテキストでの SAP からの Idoc を受信します。](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-in-a-transactional-context-using-biztalk-server.md)  
  
## <a name="see-also"></a>参照  
[SAP アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)
---
title: "Biztalk アダプターを使用して、SAP アプリケーションの開発 |Microsoft ドキュメント"
description: "BizTalk アダプター パック (BAP) と WCF、BizTalk Server、または ADO.NET を使用して、SAP アプリケーションを作成します。"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- how to, use adapters
- adapters, working with
- working with adapters
ms.assetid: e8315c0d-923b-433e-9d11-4e8a53e0a1d9
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50e8501249c460285f6f8dd429f8990d39e810e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="develop-your-sap-applications"></a>SAP アプリケーションを開発します。

## <a name="overview"></a>概要
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドします。 クライアント アプリケーションが使用できる、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP アイテムの操作を呼び出します。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]消費されることができます。  
  
-   物理ポートのバインディングを介して、[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]ソリューションです。  
  
-   クライアント プロキシのインスタンス上のメソッドの呼び出しです。  
  
-   としてホストされる WCF サービスを使用します。  
  
-   WCF チャネル モデルを使用するコードでのチャネル インスタンス経由で SOAP メッセージを送信します。  
  
-   ADO.NET インターフェイスです。  

## <a name="biztalk-vs-wcf-service-vs-wcf-channel-vs-adonet"></a>BizTalk と WCF サービスと WCF チャネルと ADO.NET
  
 次の表では:  
  
-   SAP システムを使用して、実行できるさまざまな操作を一覧表示、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
-   アプローチのかを示します ([!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、WCF サービスのモデル、WCF チャネル モデル、または ADO.NET インターフェイス)、操作を実行するために使用できます。  
  
-   選択した方法を使用するタスクの実行に関する詳細情報へのリンクを示します。  
  
|タスク|BizTalk Server|WCF サービスのモデル|WCF チャネル モデル|ADO.NET インターフェイス|  
|----------|--------------------|-----------------------|-----------------------|-----------------------|  
|SAP システムでの Rfc を呼び出す|[BizTalk Server を使用して SAP Rfc を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md)|[WCF サービス モデルを使用して SAP Rfc を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-the-wcf-service-model.md)|[WCF チャネル モデルを使用して、SAP システムに対する操作を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)|[呼び出しの Rfc および Bapi の SAP で EXEC コマンドの使用](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-and-bapis-using-the-exec-command-in-sap.md)|  
|SAP システムから受信の RFC 呼び出しの受信|[BizTalk Server を使用して SAP から受信 RFC 呼び出しの受信します。](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-from-sap-using-biztalk-server.md)|[WCF サービス モデルを使用して SAP で受信 RFC 呼び出しの受信します。](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-in-sap-using-the-wcf-service-model.md)|[WCF チャネル モデルを使用して、SAP システムからの受信操作を受信します。](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md)||  
|SAP システムで tRFCs を呼び出す|[BizTalk Server を使用して SAP で tRFCs を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-biztalk-server.md)|[WCF サービス モデルを使用して SAP で tRFCs を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-the-wcf-service-model.md)|[WCF チャネル モデルを使用して、SAP システムに対する操作を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)||  
|着信 tRFC の呼び出しを受信します。|[BizTalk Server を使用して SAP から受信 tRFC の呼び出しを受信します。](../../adapters-and-accelerators/adapter-sap/receive-inbound-trfc-calls-from-sap-using-biztalk-server.md)|[WCF サービス モデルを使用して SAP で受信 tRFC の呼び出しを受信します。](../../adapters-and-accelerators/adapter-sap/receive-inbound-trfc-calls-in-sap-using-the-wcf-service-model.md)|[WCF チャネル モデルを使用して、SAP システムからの受信操作を受信します。](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md)||  
|SAP システムでトランザクションを実行します。|[BizTalk Server を使用して SAP でトランザクションを BAPI を実行します。](../../adapters-and-accelerators/adapter-sap/run-bapi-transactions-in-sap-using-biztalk-server.md)|[WCF サービス モデルを使用して SAP での Bapi を呼び出し](../../adapters-and-accelerators/adapter-sap/invoke-bapis-in-sap-using-the-wcf-service-model.md)|[WCF チャネル モデルを使用して、SAP システムに対する操作を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)||  
|IDOC を SAP システムに送信します。|[BizTalk Server を使用して sap Idoc を送信します。](../../adapters-and-accelerators/adapter-sap/send-idocs-to-sap-using-biztalk-server.md)|[WCF サービス モデルを使用して sap Idoc を送信します。](../../adapters-and-accelerators/adapter-sap/send-idocs-to-sap-using-the-wcf-service-model.md)|[WCF チャネル モデルを使用して、SAP システムに対する操作を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)||  
|SAP システムから IDOC を受信|[BizTalk Server を使用して SAP からの Idoc を受信します。](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-using-biztalk-server.md)||[WCF チャネル モデルを使用して、SAP システムからの受信操作を受信します。](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md)||  

## <a name="next-steps"></a>次の手順

 次のトピックでは、プロシージャ、および使用するアプリケーションを開発する例に関する情報を提供、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]両方で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、および[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]ソリューションのプログラミングします。 

- [SAP システムへの接続を作成します。](create-a-connection-to-the-sap-system.md)
- [Visual Studio での SAP 操作のメタデータを取得します。](get-metadata-for-sap-operations-in-visual-studio.md)
- [バインドのプロパティの使用](read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)
- [ストリーミングと SAP アダプター](streaming-and-the-sap-adapter.md)
- [SAP アダプターを使用して BizTalk アプリケーションを開発します。](develop-biztalk-applications-using-the-sap-adapter.md)
- [WCF サービス モデルを使用してアプリケーションを開発します。](develop-sap-applications-using-the-wcf-service-model.md)
- [WCF チャネル モデルを使用してアプリケーションを開発します。](develop-sap-applications-using-the-wcf-channel-model.md)
- [プログラムによるメタデータを取得します。](get-metadata-programmatically-from-sap.md)
- [使用して、.NET Framework Data Provider 用 mySAP](use-the-net-framework-data-provider-for-mysap-business-suite.md)
- [SharePoint での SAP アダプターを使用します。](use-the-sap-adapter-with-sharepoint.md)
- [サンプル](samples-for-the-sap-adapter.md)
- [Svcutil.exe を使用してください。](use-the-servicemodel-metadata-utility-with-the-sap-adapter-in-biztalk.md) 
 
  
## <a name="see-also"></a>参照  
 [SAP システム接続 URI を作成します。](create-the-sap-system-connection-uri.md)
---
title: Biztalk アダプターを使用して、SAP アプリケーションの開発 |Microsoft Docs
description: BizTalk アダプター パック (BAP) と WCF、BizTalk Server、または ADO.NET を使用して SAP アプリケーションを作成します。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- how to, use adapters
- adapters, working with
- working with adapters
ms.assetid: e8315c0d-923b-433e-9d11-4e8a53e0a1d9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a023f3890eff7b3b8c846f0c2c3e15cda4c1d35
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003163"
---
# <a name="develop-your-sap-applications"></a>SAP アプリケーションを開発します。

## <a name="overview"></a>概要
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドします。 クライアント アプリケーションが使用できる、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP アイテムの操作を呼び出します。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]消費されることができます。  
  
- 物理ポートのバインドを使用する[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]ソリューション。  
  
- クライアント プロキシのインスタンスでメソッドの呼び出し。  
  
- としてホストされる WCF サービスを使用します。  
  
- によって、WCF チャネル モデルを使用するコードでのチャネル インスタンス経由で SOAP メッセージを送信します。  
  
- ADO.NET インターフェイス。  

## <a name="biztalk-vs-wcf-service-vs-wcf-channel-vs-adonet"></a>BizTalk と WCF サービスと WCF チャネルと ADO.NET
  
 次の表では:  
  
- 使用して SAP システムで実行できるさまざまな操作を一覧表示、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
- アプローチのかを示します ([!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、WCF サービス モデル、WCF チャネル モデル、または ADO.NET インターフェイス)、操作を実行するために使用できます。  
  
- 選択した方法を使用してタスクの実行について詳細情報へのリンクを提供します。  
  
|タスク|BizTalk Server|WCF サービス モデル|WCF チャネル モデル|ADO.NET インターフェイス|  
|----------|--------------------|-----------------------|-----------------------|-----------------------|  
|SAP システムでの Rfc を呼び出す|[BizTalk Server を使用して SAP で Rfc を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md)|[WCF サービス モデルを使用して SAP で Rfc を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-the-wcf-service-model.md)|[WCF チャネル モデルを使用して、SAP システムに対する操作を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)|[Rfc と EXEC コマンドを使用して SAP の Bapi を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-and-bapis-using-the-exec-command-in-sap.md)|  
|SAP システムから受信 RFC 呼び出しを受信|[BizTalk Server を使用して SAP から受信 RFC 呼び出しを受信します。](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-from-sap-using-biztalk-server.md)|[WCF サービス モデルを使用して SAP で受信 RFC 呼び出しを受信します。](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-in-sap-using-the-wcf-service-model.md)|[WCF チャネル モデルを使用して、SAP システムからの受信操作を受信します。](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md)||  
|SAP システムで Trfc を呼び出す|[BizTalk Server を使用して SAP の Trfc を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-biztalk-server.md)|[WCF サービス モデルを使用して SAP の Trfc を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-the-wcf-service-model.md)|[WCF チャネル モデルを使用して、SAP システムに対する操作を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)||  
|受信 tRFC 呼び出しを受信します。|[BizTalk Server を使用して SAP から受信 tRFC 呼び出しを受信します。](../../adapters-and-accelerators/adapter-sap/receive-inbound-trfc-calls-from-sap-using-biztalk-server.md)|[WCF サービス モデルを使用して SAP で受信 tRFC 呼び出しを受信します。](../../adapters-and-accelerators/adapter-sap/receive-inbound-trfc-calls-in-sap-using-the-wcf-service-model.md)|[WCF チャネル モデルを使用して、SAP システムからの受信操作を受信します。](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md)||  
|SAP システムでトランザクションを実行します。|[BizTalk Server を使用して SAP の BAPI トランザクションを実行します。](../../adapters-and-accelerators/adapter-sap/run-bapi-transactions-in-sap-using-biztalk-server.md)|[WCF サービス モデルを使用して SAP の Bapi を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-bapis-in-sap-using-the-wcf-service-model.md)|[WCF チャネル モデルを使用して、SAP システムに対する操作を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)||  
|IDOC を SAP システムに送信します。|[BizTalk Server を使用して sap の Idoc を送信します。](../../adapters-and-accelerators/adapter-sap/send-idocs-to-sap-using-biztalk-server.md)|[WCF サービス モデルを使用して sap の Idoc を送信します。](../../adapters-and-accelerators/adapter-sap/send-idocs-to-sap-using-the-wcf-service-model.md)|[WCF チャネル モデルを使用して、SAP システムに対する操作を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)||  
|SAP システムから IDOC を受信|[BizTalk Server を使用して SAP の Idoc を受信します。](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-using-biztalk-server.md)||[WCF チャネル モデルを使用して、SAP システムからの受信操作を受信します。](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md)||  

## <a name="next-steps"></a>次のステップ

 次のトピックでは、手順、および例を使用するアプリケーションを開発に関する情報を提供、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]両方で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、および[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]ソリューションをプログラミングします。 

- [SAP システムへの接続を作成する](create-a-connection-to-the-sap-system.md)
- [Visual Studio で SAP 操作のメタデータを取得する](get-metadata-for-sap-operations-in-visual-studio.md)
- [バインド プロパティの操作](read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)
- [ストリーミングと SAP アダプター](streaming-and-the-sap-adapter.md)
- [SAP アダプターを使用して BizTalk アプリケーションを開発する](develop-biztalk-applications-using-the-sap-adapter.md)
- [WCF サービス モデルを使用してアプリケーションを開発する](develop-sap-applications-using-the-wcf-service-model.md)
- [WCF チャネル モデルを使用してアプリケーションを開発する](develop-sap-applications-using-the-wcf-channel-model.md)
- [プログラムによるメタデータの取得](get-metadata-programmatically-from-sap.md)
- [使用して、.NET Framework Data Provider 用 mySAP](use-the-net-framework-data-provider-for-mysap-business-suite.md)
- [SharePoint で SAP アダプターを使用する](use-the-sap-adapter-with-sharepoint.md)
- [サンプル](samples-for-the-sap-adapter.md)
- [Svcutil.exe の使用](use-the-servicemodel-metadata-utility-with-the-sap-adapter-in-biztalk.md) 
 
  
## <a name="see-also"></a>参照  
 [SAP システム接続 URI を作成します。](create-the-sap-system-connection-uri.md)
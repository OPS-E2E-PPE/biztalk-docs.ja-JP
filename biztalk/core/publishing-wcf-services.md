---
title: "WCF サービスを公開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 70b7851b-77c1-4ab3-a61f-e7165ceb56fb
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00136b64d5feaf552f77b92b3ad4442da4e447cc
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2018
---
# <a name="publish-wcf-services"></a>WCF サービスを公開します。
オーケストレーションは、WCF クライアントが呼び出すための BizTalk Server で WCF サービスとして公開できます。  
  
## <a name="publish-wcf-services-with-the-isolated-wcf-adapters"></a>分離 WCF アダプターで WCF サービスを公開します。 
  
 WCF-BasicHttp アダプター、WCF-WSHttp アダプター、WCF-CustomIsolated アダプターなどの分離 WCF アダプターに BizTalk WCF サービス公開ウィザードを使用すると、WCF サービスを作成して公開できます。 これにより、IIS のプロセス外アプリケーションとして存在する受信場所が作成されます。  
  
 分離 WCF アダプターを使用して WCF サービスを公開する前に、インターネット インフォメーション サービス (IIS) で WCF サービスをホストする方法について理解しておく必要があります。  
  
## <a name="publish-service-metadata-for-the-wcf-receive-locations"></a>WCF 受信場所のサービス メタデータを公開します。
  
 BizTalk WCF サービス公開ウィザードを使用して、公開する WCF サービス受信場所のサービス メタデータを作成できます。 公開されたメタデータ ドキュメントからサービス モデル コードを生成するには、Windows ソフトウェア開発キット (SDK) および .NET Framework ランタイム コンポーネントに含まれている Service Model メタデータ ユーティリティ ツール (SvcUtil.exe) を使用することができます。  
  
> [!IMPORTANT]
>  BizTalk WCF サービス公開ウィザードを実行する前に、WCF サービスを有効にする必要があります。 詳細については、システム用の WCF サービスを有効にすると、次を参照してください。[分離 WCF 受信アダプタの IIS を構成する](../core/configuring-iis-for-the-isolated-wcf-receive-adapters.md)です。  
  
## <a name="next-steps"></a>次の手順
  
-   [分離 WCF 受信アダプターでの WCF サービスの公開](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [WCF 受信アダプタへのサービス メタデータの公開](../core/publishing-service-metadata-for-the-wcf-receive-adapters.md)  
  
-   [WCF 受信アダプターで WCF サービスを公開する場合の考慮事項](../core/considerations-when-publishing-wcf-services-with-the-wcf-receive-adapters.md)  
  
-   [公開済み WCF サービスでの SOAP ヘッダー](../core/soap-headers-with-published-wcf-services.md)  
  
-   [WCF サービスとして公開されたオーケストレーションからエラー例外をスローする](../core/how-to-throw-fault-exceptions-from-orchestrations-published-as-wcf-services.md)
---
title: WCF サービス公開 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 70b7851b-77c1-4ab3-a61f-e7165ceb56fb
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3cc57665a8f57fde0d1ea410c0bad4454cb1a7a4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398355"
---
# <a name="publish-wcf-services"></a>WCF サービスを公開します。
オーケストレーションは、WCF クライアントが呼び出すための BizTalk Server で WCF サービスとして公開できます。  
  
## <a name="publish-wcf-services-with-the-isolated-wcf-adapters"></a>分離 WCF アダプターで WCF サービスを公開します。 
  
 作成して、Wcf-basichttp アダプターなどの分離 WCF アダプター、Wcf-wshttp アダプターおよび Wcf-customisolated アダプターの BizTalk WCF サービス公開ウィザードを使用して WCF サービスを公開します。 これには、IIS でアプリケーションをプロセスとして存在する受信場所が作成されます。  
  
 分離 WCF アダプタを使用する WCF サービスを発行する前に、WCF サービスをホストする方法を理解するには、インターネット インフォメーション サービス (IIS) が必要です。  
  
## <a name="publish-service-metadata-for-the-wcf-receive-locations"></a>WCF 受信場所のサービス メタデータを公開します。
  
 BizTalk WCF サービス公開ウィザードを使用して公開済み WCF の受信場所に対しては、サービス メタデータを作成します。 公開されたメタデータ ドキュメントからサービス モデル コードを生成するには、Windows ソフトウェア開発キット (SDK) および .NET Framework ランタイム コンポーネントに含まれる Service Model メタデータ ユーティリティ ツール (SvcUtil.exe) を使用することができます。  
  
> [!IMPORTANT]
>  BizTalk WCF サービス公開ウィザードを実行する前に、WCF サービスを有効にする必要があります。 システム用の WCF サービスを有効にする方法の詳細については、次を参照してください。 [IIS 分離 WCF 受信アダプタを構成する](../core/configuring-iis-for-the-isolated-wcf-receive-adapters.md)します。  
  
## <a name="next-steps"></a>次のステップ
  
-   [分離 WCF 受信アダプターでの WCF サービスの公開](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [WCF 受信アダプタへのサービス メタデータの公開](../core/publishing-service-metadata-for-the-wcf-receive-adapters.md)  
  
-   [WCF 受信アダプターで WCF サービスを公開する場合の考慮事項](../core/considerations-when-publishing-wcf-services-with-the-wcf-receive-adapters.md)  
  
-   [公開済み WCF サービスでの SOAP ヘッダー](../core/soap-headers-with-published-wcf-services.md)  
  
-   [WCF サービスとして公開されたオーケストレーションからエラー例外をスローする](../core/how-to-throw-fault-exceptions-from-orchestrations-published-as-wcf-services.md)
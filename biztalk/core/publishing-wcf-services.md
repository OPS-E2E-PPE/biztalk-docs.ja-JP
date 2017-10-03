---
title: "WCF サービスの公開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- publishing, WCF services
- WCF services, publishing
ms.assetid: 70b7851b-77c1-4ab3-a61f-e7165ceb56fb
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d5f72f2b300738f2e9a1a643e152048b64cf8f55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="publishing-wcf-services"></a>WCF サービスの公開
オーケストレーションでの WCF サービスとして公開できます[!INCLUDE[btsCoName](../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] WCF クライアントによって呼び出されます。  
  
 **分離 WCF アダプターで WCF サービスの公開**  
  
 WCF-BasicHttp アダプター、WCF-WSHttp アダプター、WCF-CustomIsolated アダプターなどの分離 WCF アダプターに BizTalk WCF サービス公開ウィザードを使用すると、WCF サービスを作成して公開できます。 これにより、IIS のプロセス外アプリケーションとして存在する受信場所が作成されます。  
  
 分離 WCF アダプターを使用して WCF サービスを公開する前に、インターネット インフォメーション サービス (IIS) で WCF サービスをホストする方法について理解しておく必要があります。  
  
 **WCF 受信場所のサービス メタデータの公開**  
  
 BizTalk WCF サービス公開ウィザードを使用して、公開する WCF サービス受信場所のサービス メタデータを作成できます。 公開されたメタデータ ドキュメントからサービス モデル コードを生成するに含まれている Service Model メタデータ ユーティリティ ツール (SvcUtil.exe) を使用することができます、 [!INCLUDE[btsCoName](../includes/btsconame-md.md)] [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]ソフトウェア開発キット (SDK) の[!INCLUDE[btsWinVista](../includes/btswinvista-md.md)]と[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]ランタイム コンポーネントです。  
  
> [!IMPORTANT]
>  BizTalk WCF サービス公開ウィザードを実行する前に、WCF サービスを有効にする必要があります。 詳細については、システム用の WCF サービスを有効にすると、次を参照してください。[分離 WCF 受信アダプタの IIS を構成する](../core/configuring-iis-for-the-isolated-wcf-receive-adapters.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [発行の WCF サービスを分離 WCF 受信アダプター](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [受信アダプターの wcf サービス メタデータの公開](../core/publishing-service-metadata-for-the-wcf-receive-adapters.md)  
  
-   [受信アダプターの WCF での WCF サービスを発行するときの考慮事項](../core/considerations-when-publishing-wcf-services-with-the-wcf-receive-adapters.md)  
  
-   [公開済み WCF サービスでの SOAP ヘッダー](../core/soap-headers-with-published-wcf-services.md)  
  
-   [WCF サービスとして公開されたオーケストレーションからエラー例外をスローする方法](../core/how-to-throw-fault-exceptions-from-orchestrations-published-as-wcf-services.md)
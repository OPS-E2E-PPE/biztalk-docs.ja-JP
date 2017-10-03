---
title: "構成の IIS 分離 wcf 受信アダプター |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive adapters, WCF services
- WCF services, receive adapters
- IIS, configuring [WCF receive adapters]
ms.assetid: 1c6f1561-a7ba-4eb0-8878-bf213ebcd6a6
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1515a69ab6a9150668db4f3415f0483dd1ce4e7a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-iis-for-the-isolated-wcf-receive-adapters"></a>分離 WCF 受信アダプターのための IIS の構成
BizTalk WCF サービス公開ウィザードを使用して WCF サービスを公開するには、インターネット インフォメーション サービス (IIS)、BizTalk 分離ホスト、および Windows のユーザー グループ アカウントを構成する必要があります。 ここでは、WCF-BasicHttp 受信アダプター、WCF-WSHttp 受信アダプター、WCF-CustomIsolated アダプターなどの分離 WCF 受信アダプターを使用して WCF サービスを公開するための IIS の構成に関連する問題について説明します。 詳細については、IIS で WCF サービスをホストしているを参照してください「IIS でホストしている」 [http://go.microsoft.com/fwlink/?LinkId=75700](http://go.microsoft.com/fwlink/?LinkId=75700)です。  
  
## <a name="considerations-when-configuring-iis"></a>IIS を構成する際の考慮事項  
 **インターネット インフォメーション サービス 7.0 および 7.5**  
  
 分離 WCF 受信アダプターを使用して WCF サービスを公開するには、ASP.NET 4.0 を使用するように構成された IIS 7.0 または 7.5 を使用します。  
  
 IIS 7.0 (Windows Server 2008 SP2 の場合) および IIS 7.5 (Windows Server 2008 R2 の場合) は、IIS アプリケーション プールを使用して Web サービス要求を処理します。 IIS 7.0 は、複数のアプリケーション プールをサポートします。 それぞれのアプリケーション プールは、異なるユーザー コンテキストで実行できます。  
  
 **BizTalk 分離ホスト**  
  
 分離 WCF 受信アダプターを使用して WFC サービスをホストするには、BizTalk Server で少なくとも 1 つの分離ホストを作成する必要があります。 BizTalk 分離ホストを構成する方法の詳細についてを参照してください「BizTalk 分離ホスト」 [Web サービスを有効にすると](../core/enabling-web-services.md)です。  
  
 **複数のサーバー インストールでのデータベースへのアクセス**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] および BizTalk 管理データベースが異なるサーバーに存在する場合、IIS アプリケーション プールのユーザー コンテキストをドメイン ユーザー アカウントに変更する必要があります。  
  
 マルチサーバー展開を実装する場合、分離ホスト Windows グループは BizTalk データベース サーバーが属するドメインに存在する必要があります。  
  
 **アカウントの特権およびユーザー権限を最小限に抑える**  
  
 分離ホストを使用すると、外部プロセスで実行するアダプターに、BizTalk Server との連携に必要な最小限のリソースへのアクセス権が付与されます。 セキュリティで保護された展開を行うために、外部プロセスのユーザー コンテキストに最小限の権限を付与します。  
  
 **BizTalk Web サービス公開ウィザードのセキュリティに関する推奨事項**  
  
 BizTalk WCF サービス公開ウィザードで作成される仮想ディレクトリは、親仮想ディレクトリまたは Web サイトからアクセス制御リスト (ACL) を継承します。  
  
## <a name="see-also"></a>参照  
 [WCF サービスの公開](../core/publishing-wcf-services.md)
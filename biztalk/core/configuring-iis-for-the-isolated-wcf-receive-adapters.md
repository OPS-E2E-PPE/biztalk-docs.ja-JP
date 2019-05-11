---
title: 受信アダプターの IIS 分離 WCF の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive adapters, WCF services
- WCF services, receive adapters
- IIS, configuring [WCF receive adapters]
ms.assetid: 1c6f1561-a7ba-4eb0-8878-bf213ebcd6a6
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 477afeef37fdf62ecbbd5dc78d11bcf20b5fbd48
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390921"
---
# <a name="configuring-iis-for-the-isolated-wcf-receive-adapters"></a>構成の IIS 分離 wcf 受信アダプター
を、BizTalk WCF サービス公開ウィザードを使用して WCF サービスを発行するには、インターネット インフォメーション サービス (IIS)、BizTalk 分離ホスト、および Windows ユーザー グループ アカウントを構成する必要があります。 このセクションには、Wcf-basichttp 受信アダプターなどの分離 WCF を使用した WCF サービスの公開受信アダプター用の IIS の構成に関連する問題がについて説明します、Wcf-wshttp 受信アダプター、Wcf-customisolated アダプター。 IIS で WCF サービスをホストする方法の概要についてで「IIS でホスト」を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=75700](http://go.microsoft.com/fwlink/?LinkId=75700)します。  
  
## <a name="considerations-when-configuring-iis"></a>IIS を構成する際の考慮事項  
 **インターネット インフォメーション サービス 7.0 および 7.5**  
  
 受信アダプターの分離 WCF を使用した WCF サービスを公開する ASP.NET 4.0 で構成されている 7.5 および IIS 7.0 を使用できます。  
  
 (Windows Server 2008 SP2) の IIS 7.0 および IIS 7.5 (Windows Server 2008 R2) は、Web サービス要求を処理するため、IIS アプリケーション プールを使用します。 IIS 7.0 では、複数のアプリケーション プールをサポートします。 各アプリケーション プール プロセスは、別のユーザー コンテキストで実行できます。  
  
 **BizTalk 分離ホスト**  
  
 WCF をホストするサービスと WCF 分離受信アダプター、BizTalk Server で少なくとも 1 つの分離ホストを作成する必要があります。 BizTalk 分離ホストを構成する方法の詳細についてを参照してください「BizTalk 分離ホスト」 [Web サービスを有効にする](../core/enabling-web-services.md)します。  
  
 **複数のサーバー インストールでのデータベースへのアクセス**  
  
 場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と BizTalk 管理データベースが別のサーバーに存在する、ドメイン ユーザー アカウントに、IIS アプリケーション プールのユーザー コンテキストを変更する必要があります。  
  
 マルチ サーバー展開を実装する場合は、分離ホスト Windows グループが BizTalk データベース サーバーが属するドメインに存在する必要があります。  
  
 **アカウントの特権およびユーザー権限を最小限に抑える**  
  
 分離ホストを使用して、BizTalk Server との対話に必要なリソース量が最小限に外部プロセスへのアクセスで実行されるアダプターを与えます。 セキュリティで保護された展開は、するようにユーザー コンテキスト、外部プロセスの最小限の特権します。  
  
 **BizTalk Web サービス公開ウィザードのセキュリティに関する推奨事項**  
  
 BizTalk WCF サービス公開ウィザードによって作成された仮想ディレクトリは、親仮想ディレクトリまたは Web サイトからのアクセス制御リスト (ACL) を継承します。  
  
## <a name="see-also"></a>参照  
 [WCF サービスの公開](../core/publishing-wcf-services.md)
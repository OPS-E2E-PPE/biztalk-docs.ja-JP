---
title: Windows アカウントをセキュリティで保護された分散型 BizTalk Server の展開 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Server, Windows groups
- user accounts, naming conventions
- user accounts
- access control, Windows groups
- security, access control
- architecture, security
- security, Windows accounts
- administrator accounts
- user accounts, administrators
- architecture, large distributions
ms.assetid: 2a0893ef-8bfb-481b-b024-7f7d6e2a6f09
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 493f0e9e095a5de8b1fc57eec658981ea3befa88
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401566"
---
# <a name="windows-accounts-for-a-secure-distributed-biztalk-server-deployment"></a>セキュリティで保護された分散型 BizTalk Server 展開向けの Windows アカウント
BizTalk Server の展開のシステム アーキテクチャの詳細については、次を参照してください。 [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)します。  
  
 このセクションでは、分散型 BizTalk Server 環境の Windows グループとアカウントを作成するための推奨事項について説明します。 グループ名とアカウント名は、グループとアカウントの機能に基づいた提案です。 これらのグループとアカウントの名前は自由に選択できます。 分散型 BizTalk Server アーキテクチャの詳細については、次を参照してください。[大規模な分散アーキテクチャ](../core/large-distributed-architecture.md)します。  
  
## <a name="windows-groups-for-a-secure-distributed-biztalk-server-deployment"></a>セキュリティで保護された分散型 BizTalk Server 展開向けの Windows グループ  
 次の表は、ドメイン管理者によりデータ層内のドメイン コントローラーに作成することが推奨される Windows グループを示しています。  
  
- SSO 管理者  
  
- SSO 関連管理者  
  
- BizTalk Server 管理者  
  
- BizTalk Server オペレータ  
  
  BizTalk Server で使用される Windows グループの詳細については、次を参照してください。 [Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)します。  
  
  次の表は、上記のドメイン グループ以外に、ドメイン管理者がデータ層内のドメイン コントローラーに作成する、セキュリティで保護された展開専用の追加グループを示しています。  
  
|グループ名 (推奨)|用途|  
|------------------------------|-------------|  
|BizTalk 処理ホスト ユーザー 1|メッセージの処理に使用する特定のインプロセス ホストのホスト インスタンス用グループ。 BizTalk Server 環境でメッセージの処理に使用する各インプロセス ホスト用のグループを作成します。|  
|BizTalk 送信ホスト ユーザー 1|メッセージの送信に使用する特定のインプロセス ホストのホスト インスタンス用グループ。 BizTalk Server 環境でメッセージの送信に使用する各インプロセス ホスト用のグループを作成します。|  
|BizTalk 受信ホスト ユーザー 1|メッセージの受信に使用する特定のインプロセス ホストのホスト インスタンス用グループ。 BizTalk Server 環境でメッセージの受信に使用する各インプロセス ホスト用のグループを作成します。|  
|BizTalk 追跡ホスト ユーザー|追跡専用に使用する BizTalk ホスト用グループ。|  
|BizTalk SOAP ユーザー|SOAP アダプターに使用する分離ホストのホスト インスタンス用グループ。|  
|BizTalk HTTP ユーザー|HTTP アダプターに使用する分離ホストのホスト インスタンス用グループ。|  
  
 ドメイン管理者は、企業ドメインのドメイン コントローラーに次のグループを作成する必要があります。  
  
-   BizTalk BAM Portal ユーザー  
  
## <a name="windows-user-or-service-accounts-for-a-secure-distributed-biztalk-server-deployment"></a>セキュリティで保護された分散型 BizTalk Server 展開向けの Windows ユーザーまたはサービス アカウント  
 次の表は、ドメイン管理者によりデータ ドメインのドメイン コントローラーに作成することが推奨されるアカウントを示しています。 ドメイン管理者は、アカウントが対象グループのメンバーであることを確認する必要があります。  
  
 BizTalk Server で使用されるユーザー アカウントについての詳細については、次を参照してください。 [Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)します。  
  
|アカウント名 (例)|型|グループのメンバー|  
|------------------------------|----------|---------------------|  
|SSO 管理者|ユーザー|SSO 管理者|  
|SSO サービス|サービス|SSO 管理者|  
|SSO マスター シークレット|サービス|SSO 管理者|  
|BizTalk 管理者|ユーザー|BizTalk 管理者<br /><br /> SSO 関連管理者|  
|BizTalk オペレーター|ユーザー|BizTalk Operators|  
|BizTalk 処理 1|サービス|BizTalk 処理ホスト ユーザー 1|  
|2 を処理する BizTalk**に注意してください。** 環境内の各処理ホストの複数のアカウントを作成できます。|サービス|BizTalk 処理ホスト ユーザー 1|  
|BizTalk 追跡|サービス|BizTalk 追跡ホスト ユーザー|  
|SOAP アダプター|サービス|BizTalk SOAP ユーザー|  
|HTTP アダプター|サービス|BizTalk HTTP ユーザー|  
|ルール エンジン更新サービス|サービス||  
|インストール|ユーザー|SSO 管理者 (だけのマスター シークレット サーバーを構成する)<br /><br /> ローカル管理者<br /><br /> sysadmin SQL Server ロール<br /><br /> OLAP 管理者|  
|BAM アプリケーション プール|サービス|IIS_WPG|  
|BAM 管理|サービス|IIS_WPG|  
|BAM 通知|サービス|SQLServer2005NotificationServicesUser$\<**ComputerName**\>|  
  
 次の表は、ドメイン管理者により企業ドメインのドメイン コントローラーに作成することが推奨されるアカウントを示しています。  
  
|アカウント名|型|  
|------------------|----------|  
|SharePoint 管理者|ユーザー|  
|SharePoint サイト適格者|ユーザー|  
  
## <a name="see-also"></a>参照  
 [大規模な分散アーキテクチャ](../core/large-distributed-architecture.md)   
 [セキュリティ保護のための最小ユーザー権限](../core/minimum-security-user-rights.md)   
 [Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)   
 [BizTalk Server のサンプル アーキテクチャ](../core/sample-biztalk-server-architectures.md)
---
title: ドメイン グループ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9adc090e-e18c-46b6-b985-49b200d42966
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afa529aa98f0eee379f4e2000970549ab9305a20
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389320"
---
# <a name="domain-groups-in-biztalk"></a>BizTalk 内のドメイン グループ
また、ドメイン グループ アカウントとドメイン ユーザー アカウントは、単一および複数の両方のコンピュータ構成でサポートされます。 複数コンピュータ構成の場合、このセクション、およびインストール ガイドの「マルチサーバー環境に関する注意点 (Considerations for Multiserver Environments)」で示す要件を満たす必要があります。 詳細については、次を参照してください。、[インストールの概要](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)します。  
  
## <a name="before-you-begin"></a>アンインストールの準備
-   BizTalk Server の構成にドメイン グループを使用する場合は、BizTalk Server を構成する前に、グループを手動で作成しておく必要があります。 構成マネージャーでは、ドメイン グループを作成できません。  
  
-   ドメイン グループやユーザー アカウントを作成した後でグループ所属団体に従って、適切なグループにユーザー アカウントを追加[Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)します。  
  
-   使用 **\<DomainName\>\\< ユーザー名\>** in Configuration Manager のドメイン アカウント情報を指定する場合。  
  
-   BizTalk Server では、すべてのクラスタリング シナリオに対応するドメイン アカウントが必要です。 クラスタ化された SQL Server やクラスタ化された SSO サーバー (マスタ シークレット サーバー) で、ローカル アカウントを使用することはできません。  
  
-   インストールして、BizTalk Server を構成する管理者は、次のグループのメンバーである必要があります。SSO 管理者 (マスタ シークレット サーバーを構成する) の場合のみです。ローカルの管理者sysadmin SQL Server ロール。OLAP 管理者。  
  
> [!NOTE]
>  SSO 管理者と SSO 関連管理者の構成中にドメイン グループを指定し、その操作を行うための十分な権限がある場合、ドメイン グループは自動的に作成されます。 十分な権限がない場合は、これらのドメイン グループが既に存在することを確認します。  
  
## <a name="see-also"></a>参照  
 [ローカル グループ](../core/local-groups.md)   
 [インストールの概要](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)   
 [BizTalk Server の Windows グループ アカウントとユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)

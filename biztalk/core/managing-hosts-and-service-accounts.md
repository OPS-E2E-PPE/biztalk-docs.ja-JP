---
title: ホストおよびサービス アカウントの管理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, managing
- managing [user accounts]
- service accounts, security
- managing [hosts], security
- security, hosts
- managing [Windows groups]
- hosts, security
- security, service accounts
- Windows groups, managing
- user accounts, managing
ms.assetid: 25797571-f1f9-42a4-8fff-5b03076bbe36
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0099e683fba7c5f4e2400ad2f9ce005928b0a2aa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262386"
---
# <a name="managing-hosts-and-service-accounts"></a>ホストとサービス アカウントの管理
BizTalk Server の構成が済んだら、Windows グループおよびユーザー アカウントを管理する必要があります。 ここでは、BizTalk Server に必要なアカウントを管理する方法について説明します。  
  
> [!NOTE]
>  BizTalk Server の複数サーバー環境では、ドメイン グローバル グループを使用する必要があります。 BizTalk Server の単一サーバー環境では、ドメイン グローバル グループを使用することも、ローカル グループを使用することもできます。  
  
 次のタスクは、Windows 管理者として実行する必要があります。  
  
-   ホスト Windows グループを作成する  
  
-   各ホスト インスタンスのサービス アカウントを作成する  
  
-   ホスト Windows グループにサービス アカウントを追加する  
  
-   ホストに関連付けられている Windows グループに変更を加える  
  
 完全な一覧と、グループと BizTalk Server でユーザー アカウントの説明では、次を参照してください。 [Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)です。  
  
 管理タスクのセキュリティの最小ユーザー権限の詳細については、次を参照してください。[最小セキュリティ ユーザー権限](../core/minimum-security-user-rights.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [新しいホストとホスト インスタンスのアカウントをサービスを作成する方法](../core/how-to-create-service-accounts-for-new-hosts-and-host-instances.md)  
  
-   [サービス アカウントとパスワードを変更する方法](../core/how-to-change-service-accounts-and-passwords.md)
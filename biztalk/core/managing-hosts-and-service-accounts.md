---
title: ホストとサービス アカウントの管理 |Microsoft Docs
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
ms.openlocfilehash: f0f33a484d67981bb72908243b82e7835e0390e3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016116"
---
# <a name="managing-hosts-and-service-accounts"></a>ホストとサービス アカウントの管理
BizTalk Server の構成が済んだら、Windows グループおよびユーザー アカウントを管理する必要があります。 ここでは、BizTalk Server に必要なアカウントを管理する方法について説明します。  
  
> [!NOTE]
>  BizTalk Server の複数サーバー環境では、ドメイン グローバル グループを使用する必要があります。 BizTalk Server の単一サーバー環境では、ドメイン グローバル グループを使用することも、ローカル グループを使用することもできます。  
  
 次のタスクは、Windows 管理者として実行する必要があります。  
  
- ホスト Windows グループを作成する  
  
- 各ホスト インスタンスのサービス アカウントを作成する  
  
- ホスト Windows グループにサービス アカウントを追加する  
  
- ホストに関連付けられている Windows グループに変更を加える  
  
  完全な一覧と、グループと BizTalk Server でユーザー アカウントの説明では、次を参照してください。 [Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)します。  
  
  最低限のセキュリティ ユーザー権利の管理タスクの詳細については、次を参照してください。[最小セキュリティ ユーザー権限](../core/minimum-security-user-rights.md)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [新しいホストとホスト インスタンスのアカウントをサービスを作成する方法](../core/how-to-create-service-accounts-for-new-hosts-and-host-instances.md)  
  
-   [サービス アカウントとパスワードを変更する方法](../core/how-to-change-service-accounts-and-passwords.md)
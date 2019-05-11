---
title: 新しいホストとホスト インスタンスのアカウントをサービスを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Configuration Manager, service accounts
- Windows groups, service accounts
- Configuration Manager
- service accounts, Windows groups
- hosts, service accounts
- service accounts, hosts
- service accounts, Configuration Manager
- service accounts, creating
- creating, service accounts
ms.assetid: cef97f4a-8db1-41b6-9614-608c2fbf59a9
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 983cbb2b21b2a9027830f9bad326798b84c0f2bc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385402"
---
# <a name="how-to-create-service-accounts-for-new-hosts-and-host-instances"></a>新しいホストとホスト インスタンスのアカウントをサービスを作成する方法
Configuration Manager では、インストールして 1 台のコンピューターで BizTalk Server を構成するときに必要な Windows グループとユーザー アカウントを構成します。  
  
 手動で Windows グループとユーザー アカウントを作成し、Configuration Manager を実行する前に、ドメイン環境で Windows グループにユーザー アカウントを追加する必要があります。 詳細については、次を参照してください。[ドメイン グループ](../core/domain-groups.md)します。  
  
 新しいホストまたはホスト インスタンスを作成する前に、次の手順を実行する必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行する管理者または Domain Admins グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-create-service-accounts-for-new-hosts-or-host-instances"></a>新しいホストまたはホスト インスタンス サービス アカウントを作成するには  
  
1.  作成する新しいホストのホスト Windows グループを作成します。 新しいホストを作成する方法の詳細については、次を参照してください。[新しいホストを作成する方法](../core/how-to-create-a-new-host.md)します。  
  
2.  新しいホストに追加される各ホスト インスタンス サービス アカウントを作成します。 新しいホスト インスタンスを作成する方法の詳細については、次を参照してください。[ホスト インスタンスを追加する方法](../core/how-to-add-a-host-instance.md)します。  
  
3.  必要に応じて、ホスト Windows グループにサービス アカウントを追加します。 これには、サービス アカウントを追加する必要があります Windows グループの詳細については、次を参照してください。 [Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)します。  
  
4.  Windows グループを使用して、ホストとホスト インスタンスを作成するときに、サービス アカウント。  
  
    > [!NOTE]
    >  指定しない\<*コンピューター名*\>\ ローカル グループを含む 1 台のコンピューターのセットアップでプレフィックスとして。  
  
    > [!NOTE]
    >  ドメイン グループを使用しているかどうか、指定する必要あります\<*ドメイン NetBIOS 名*\>\ ホスト Windows グループ名のプレフィックスとして。 たとえば、CONTOSO\btssvc です。  
  
## <a name="see-also"></a>参照  
 [ホストの管理とサービス アカウント](../core/managing-hosts-and-service-accounts.md)   
 [BizTalk Server のセキュリティを管理します。](../core/managing-biztalk-server-security.md)   
 [BizTalk Server 管理者グループを管理する方法](../core/how-to-manage-the-biztalk-server-administrators-group.md)   
 [Windows グループおよびユーザー アカウントの管理のベスト プラクティス](../core/best-practices-for-managing-windows-groups-and-user-accounts.md)
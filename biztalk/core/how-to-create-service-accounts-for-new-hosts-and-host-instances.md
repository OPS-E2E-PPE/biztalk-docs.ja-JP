---
title: "新しいホストとホスト インスタンスのアカウントをサービスを作成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3626f4349fa1e2cc9f739cf0375ab73e3adc7ae0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-service-accounts-for-new-hosts-and-host-instances"></a>新しいホストおよびホスト インスタンスのサービス アカウントを作成する方法
BizTalk Server を 1 台のコンピュータにインストールした場合、必要な Windows グループ アカウントとユーザー アカウントが構成マネージャで構成されます。  
  
 構成マネージャを実行する前に、ドメイン環境において、Windows グループおよびユーザー アカウントを手動で作成して Windows グループに追加する必要があります。 詳細については、次を参照してください。[ドメイン グループ](../core/domain-groups.md)です。  
  
 新しいホストまたはホスト インスタンスを作成する前に、以下の手順を実行する必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、管理者グループまたはドメイン管理者グループのメンバとしてログオンする必要があります。  
  
### <a name="to-create-service-accounts-for-new-hosts-or-host-instances"></a>新しいホストまたはホスト インスタンスのサービス アカウントを作成するには  
  
1.  作成する新しいホストのホスト Windows グループを作成します。 新しいホストの作成の詳細については、次を参照してください。[を新しいホストを作成する方法](../core/how-to-create-a-new-host.md)です。  
  
2.  新しいホストに追加する各ホスト インスタンスのサービス アカウントを作成します。 新しいホスト インスタンスの作成の詳細については、次を参照してください。[ホスト インスタンスを追加する方法](../core/how-to-add-a-host-instance.md)です。  
  
3.  必要に応じて、ホスト Windows グループにサービス アカウントを追加します。 先には、サービス アカウントを追加する必要があります Windows グループについては、次を参照してください。 [Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)です。  
  
4.  ホストおよびホスト インスタンスを作成する場合は、この Windows グループおよびサービス アカウントを使用します。  
  
    > [!NOTE]
    >  指定しない\<*コンピューター名*> \ ローカル グループと 1 台のコンピューターのセットアップ時にプレフィックスとして。  
  
    > [!NOTE]
    >  ドメイン グループを使用するかどうか、必要がありますを指定する\<*ドメイン NetBIOS 名*> \ ホスト Windows グループ名のプレフィックスとして。 CONTOSO\btssvc などの名前で保存してください。  
  
## <a name="see-also"></a>参照  
 [管理ホストおよびサービス アカウント](../core/managing-hosts-and-service-accounts.md)   
 [BizTalk Server のセキュリティを管理します。](../core/managing-biztalk-server-security.md)   
 [BizTalk Server 管理者グループを管理する方法](../core/how-to-manage-the-biztalk-server-administrators-group.md)   
 [Windows グループとユーザー アカウントを管理するためのベスト プラクティス](../core/best-practices-for-managing-windows-groups-and-user-accounts.md)
---
title: 新しいホストとホスト インスタンスのアカウントをサービスを作成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 5d4887d78466340b12b95ed43d27523955ab0689
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969377"
---
# <a name="how-to-create-service-accounts-for-new-hosts-and-host-instances"></a><span data-ttu-id="638c4-102">新しいホストおよびホスト インスタンスのサービス アカウントを作成する方法</span><span class="sxs-lookup"><span data-stu-id="638c4-102">How to Create Service Accounts for New Hosts and Host Instances</span></span>
<span data-ttu-id="638c4-103">BizTalk Server を 1 台のコンピュータにインストールした場合、必要な Windows グループ アカウントとユーザー アカウントが構成マネージャで構成されます。</span><span class="sxs-lookup"><span data-stu-id="638c4-103">The Configuration Manager configures the necessary Windows groups and user accounts when you install and configure BizTalk Server on a single computer.</span></span>  
  
 <span data-ttu-id="638c4-104">構成マネージャを実行する前に、ドメイン環境において、Windows グループおよびユーザー アカウントを手動で作成して Windows グループに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="638c4-104">You must manually create Windows groups and user accounts, and add the user accounts to the Windows groups in a domain environment before running the Configuration Manager.</span></span> <span data-ttu-id="638c4-105">詳細については、次を参照してください。[ドメイン グループ](../core/domain-groups.md)です。</span><span class="sxs-lookup"><span data-stu-id="638c4-105">For more information, see [Domain Groups](../core/domain-groups.md).</span></span>  
  
 <span data-ttu-id="638c4-106">新しいホストまたはホスト インスタンスを作成する前に、以下の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="638c4-106">You must perform the following procedure before creating a new host or host instance.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="638c4-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="638c4-107">Prerequisites</span></span>  
 <span data-ttu-id="638c4-108">ここで示す手順を実行するには、管理者グループまたはドメイン管理者グループのメンバとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="638c4-108">You must be logged on as a member of Administrators or Domain Admins group to perform this procedure.</span></span>  
  
### <a name="to-create-service-accounts-for-new-hosts-or-host-instances"></a><span data-ttu-id="638c4-109">新しいホストまたはホスト インスタンスのサービス アカウントを作成するには</span><span class="sxs-lookup"><span data-stu-id="638c4-109">To create service accounts for new hosts or host instances</span></span>  
  
1.  <span data-ttu-id="638c4-110">作成する新しいホストのホスト Windows グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="638c4-110">Create a host Windows group for the new host that you will create.</span></span> <span data-ttu-id="638c4-111">新しいホストの作成の詳細については、次を参照してください。[を新しいホストを作成する方法](../core/how-to-create-a-new-host.md)です。</span><span class="sxs-lookup"><span data-stu-id="638c4-111">For more information about creating a new host, see [How to Create a New Host](../core/how-to-create-a-new-host.md).</span></span>  
  
2.  <span data-ttu-id="638c4-112">新しいホストに追加する各ホスト インスタンスのサービス アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="638c4-112">Create service accounts for each host instance that will be added to the new host.</span></span> <span data-ttu-id="638c4-113">新しいホスト インスタンスの作成の詳細については、次を参照してください。[ホスト インスタンスを追加する方法](../core/how-to-add-a-host-instance.md)です。</span><span class="sxs-lookup"><span data-stu-id="638c4-113">For more information about creating a new host instance, see [How to Add a Host Instance](../core/how-to-add-a-host-instance.md).</span></span>  
  
3.  <span data-ttu-id="638c4-114">必要に応じて、ホスト Windows グループにサービス アカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="638c4-114">Add the service accounts to the host Windows group as needed.</span></span> <span data-ttu-id="638c4-115">先には、サービス アカウントを追加する必要があります Windows グループについては、次を参照してください。 [Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="638c4-115">For information about the Windows groups to which you must add the service account, see [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
4.  <span data-ttu-id="638c4-116">ホストおよびホスト インスタンスを作成する場合は、この Windows グループおよびサービス アカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="638c4-116">Use the Windows group and service account when creating the host and host instances.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="638c4-117">指定しない\<*コンピューター名*\>\ ローカル グループと 1 台のコンピューターのセットアップ時にプレフィックスとして。</span><span class="sxs-lookup"><span data-stu-id="638c4-117">Do not specify \<*computer name*\>\ as the prefix in a single computer setup with local groups.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="638c4-118">ドメイン グループを使用するかどうか、必要がありますを指定する\<*ドメイン NetBIOS 名*\>\ ホスト Windows グループ名のプレフィックスとして。</span><span class="sxs-lookup"><span data-stu-id="638c4-118">If you are using a Domain group, you must specify \<*Domain NetBIOS Name*\>\ as the prefix for the host Windows Group name.</span></span> <span data-ttu-id="638c4-119">CONTOSO\btssvc などの名前で保存してください。</span><span class="sxs-lookup"><span data-stu-id="638c4-119">For example, CONTOSO\btssvc.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="638c4-120">参照</span><span class="sxs-lookup"><span data-stu-id="638c4-120">See Also</span></span>  
 <span data-ttu-id="638c4-121">[管理ホストおよびサービス アカウント](../core/managing-hosts-and-service-accounts.md) </span><span class="sxs-lookup"><span data-stu-id="638c4-121">[Managing Hosts and Service Accounts](../core/managing-hosts-and-service-accounts.md) </span></span>  
 <span data-ttu-id="638c4-122">[BizTalk Server のセキュリティを管理します。](../core/managing-biztalk-server-security.md) </span><span class="sxs-lookup"><span data-stu-id="638c4-122">[Managing BizTalk Server Security](../core/managing-biztalk-server-security.md) </span></span>  
 <span data-ttu-id="638c4-123">[BizTalk Server 管理者グループを管理する方法](../core/how-to-manage-the-biztalk-server-administrators-group.md) </span><span class="sxs-lookup"><span data-stu-id="638c4-123">[How to Manage the BizTalk Server Administrators Group](../core/how-to-manage-the-biztalk-server-administrators-group.md) </span></span>  
 [<span data-ttu-id="638c4-124">Windows グループおよびユーザー アカウントの管理のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="638c4-124">Best Practices for Managing Windows Groups and User Accounts</span></span>](../core/best-practices-for-managing-windows-groups-and-user-accounts.md)
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
# <a name="how-to-create-service-accounts-for-new-hosts-and-host-instances"></a><span data-ttu-id="42279-102">新しいホストとホスト インスタンスのアカウントをサービスを作成する方法</span><span class="sxs-lookup"><span data-stu-id="42279-102">How to Create Service Accounts for New Hosts and Host Instances</span></span>
<span data-ttu-id="42279-103">Configuration Manager では、インストールして 1 台のコンピューターで BizTalk Server を構成するときに必要な Windows グループとユーザー アカウントを構成します。</span><span class="sxs-lookup"><span data-stu-id="42279-103">The Configuration Manager configures the necessary Windows groups and user accounts when you install and configure BizTalk Server on a single computer.</span></span>  
  
 <span data-ttu-id="42279-104">手動で Windows グループとユーザー アカウントを作成し、Configuration Manager を実行する前に、ドメイン環境で Windows グループにユーザー アカウントを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42279-104">You must manually create Windows groups and user accounts, and add the user accounts to the Windows groups in a domain environment before running the Configuration Manager.</span></span> <span data-ttu-id="42279-105">詳細については、次を参照してください。[ドメイン グループ](../core/domain-groups.md)します。</span><span class="sxs-lookup"><span data-stu-id="42279-105">For more information, see [Domain Groups](../core/domain-groups.md).</span></span>  
  
 <span data-ttu-id="42279-106">新しいホストまたはホスト インスタンスを作成する前に、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42279-106">You must perform the following procedure before creating a new host or host instance.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="42279-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="42279-107">Prerequisites</span></span>  
 <span data-ttu-id="42279-108">この手順を実行する管理者または Domain Admins グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="42279-108">You must be logged on as a member of Administrators or Domain Admins group to perform this procedure.</span></span>  
  
### <a name="to-create-service-accounts-for-new-hosts-or-host-instances"></a><span data-ttu-id="42279-109">新しいホストまたはホスト インスタンス サービス アカウントを作成するには</span><span class="sxs-lookup"><span data-stu-id="42279-109">To create service accounts for new hosts or host instances</span></span>  
  
1.  <span data-ttu-id="42279-110">作成する新しいホストのホスト Windows グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="42279-110">Create a host Windows group for the new host that you will create.</span></span> <span data-ttu-id="42279-111">新しいホストを作成する方法の詳細については、次を参照してください。[新しいホストを作成する方法](../core/how-to-create-a-new-host.md)します。</span><span class="sxs-lookup"><span data-stu-id="42279-111">For more information about creating a new host, see [How to Create a New Host](../core/how-to-create-a-new-host.md).</span></span>  
  
2.  <span data-ttu-id="42279-112">新しいホストに追加される各ホスト インスタンス サービス アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="42279-112">Create service accounts for each host instance that will be added to the new host.</span></span> <span data-ttu-id="42279-113">新しいホスト インスタンスを作成する方法の詳細については、次を参照してください。[ホスト インスタンスを追加する方法](../core/how-to-add-a-host-instance.md)します。</span><span class="sxs-lookup"><span data-stu-id="42279-113">For more information about creating a new host instance, see [How to Add a Host Instance](../core/how-to-add-a-host-instance.md).</span></span>  
  
3.  <span data-ttu-id="42279-114">必要に応じて、ホスト Windows グループにサービス アカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="42279-114">Add the service accounts to the host Windows group as needed.</span></span> <span data-ttu-id="42279-115">これには、サービス アカウントを追加する必要があります Windows グループの詳細については、次を参照してください。 [Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="42279-115">For information about the Windows groups to which you must add the service account, see [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
4.  <span data-ttu-id="42279-116">Windows グループを使用して、ホストとホスト インスタンスを作成するときに、サービス アカウント。</span><span class="sxs-lookup"><span data-stu-id="42279-116">Use the Windows group and service account when creating the host and host instances.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="42279-117">指定しない\<*コンピューター名*\>\ ローカル グループを含む 1 台のコンピューターのセットアップでプレフィックスとして。</span><span class="sxs-lookup"><span data-stu-id="42279-117">Do not specify \<*computer name*\>\ as the prefix in a single computer setup with local groups.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="42279-118">ドメイン グループを使用しているかどうか、指定する必要あります\<*ドメイン NetBIOS 名*\>\ ホスト Windows グループ名のプレフィックスとして。</span><span class="sxs-lookup"><span data-stu-id="42279-118">If you are using a Domain group, you must specify \<*Domain NetBIOS Name*\>\ as the prefix for the host Windows Group name.</span></span> <span data-ttu-id="42279-119">たとえば、CONTOSO\btssvc です。</span><span class="sxs-lookup"><span data-stu-id="42279-119">For example, CONTOSO\btssvc.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42279-120">参照</span><span class="sxs-lookup"><span data-stu-id="42279-120">See Also</span></span>  
 <span data-ttu-id="42279-121">[ホストの管理とサービス アカウント](../core/managing-hosts-and-service-accounts.md) </span><span class="sxs-lookup"><span data-stu-id="42279-121">[Managing Hosts and Service Accounts](../core/managing-hosts-and-service-accounts.md) </span></span>  
 <span data-ttu-id="42279-122">[BizTalk Server のセキュリティを管理します。](../core/managing-biztalk-server-security.md) </span><span class="sxs-lookup"><span data-stu-id="42279-122">[Managing BizTalk Server Security](../core/managing-biztalk-server-security.md) </span></span>  
 <span data-ttu-id="42279-123">[BizTalk Server 管理者グループを管理する方法](../core/how-to-manage-the-biztalk-server-administrators-group.md) </span><span class="sxs-lookup"><span data-stu-id="42279-123">[How to Manage the BizTalk Server Administrators Group](../core/how-to-manage-the-biztalk-server-administrators-group.md) </span></span>  
 [<span data-ttu-id="42279-124">Windows グループおよびユーザー アカウントの管理のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="42279-124">Best Practices for Managing Windows Groups and User Accounts</span></span>](../core/best-practices-for-managing-windows-groups-and-user-accounts.md)
---
title: グループおよびサービス アカウントのアクセス制御 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- access control, service accounts
- user accounts, default accounts
- service accounts, security
- user accounts, unsupported
- access control, groups
- service accounts, access control
- groups, access control
- groups, security
ms.assetid: 411a7bfa-6675-4d09-9e37-83e2941df3c6
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f3e34d34f9b6a79b1379c98aa362c266a52424c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362066"
---
# <a name="access-control-for-groups-and-service-accounts"></a><span data-ttu-id="9f0f4-102">グループおよびサービス アカウントのアクセス制御</span><span class="sxs-lookup"><span data-stu-id="9f0f4-102">Access Control for Groups and Service Accounts</span></span>
<span data-ttu-id="9f0f4-103">各 BizTalk ホスト インスタンスは、ユーザーが作成したサービス アカウントで実行されます。</span><span class="sxs-lookup"><span data-stu-id="9f0f4-103">Each BizTalk Host instance runs under a user-created service account.</span></span> <span data-ttu-id="9f0f4-104">サービス アカウントを指定する必要があり、時に、パスワード、コンピューター上にホスト インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="9f0f4-104">You must provide the service accounts and their passwords at the time you create the host instance on a computer.</span></span> <span data-ttu-id="9f0f4-105">BizTalk Server では、次のアカウントに、さらに、追加されることをホストするには特定の SQL Server データベース ロールにローカルまたはドメイン Windows グループに各サービス アカウントを追加することで、ジョブの実行に必要な最小ユーザー権限があることによりできます。</span><span class="sxs-lookup"><span data-stu-id="9f0f4-105">BizTalk Server then ensures that the accounts have the minimum user rights needed to do their jobs by adding each of these service accounts to a local or domain Windows group that, in turn, it adds to the SQL Server Database role specific to that host.</span></span>  
  
 <span data-ttu-id="9f0f4-106">このアプローチには次の利点があります。</span><span class="sxs-lookup"><span data-stu-id="9f0f4-106">This approach offers the following benefits:</span></span>  
  
- <span data-ttu-id="9f0f4-107">付与できます各ホスト インスタンスに異なるサービス アカウントにサーバーをオフラインにしなくても、各ホスト インスタンス用のパスワードを変更できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9f0f4-107">You can give each host instance a distinct service account, making it possible to change the passwords for each host instance without having to take servers offline.</span></span> <span data-ttu-id="9f0f4-108">サービスを中断せず、パスワードのローリング更新プログラムを実行できます。</span><span class="sxs-lookup"><span data-stu-id="9f0f4-108">You can perform rolling password updates without interrupting service.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="9f0f4-109">認証が信頼済みであるホストと信頼されている認証ではないホストを同じサービス アカウントを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="9f0f4-109">You cannot use the same service account for hosts that are authentication trusted and hosts that are not authentication trusted.</span></span>  
  
- <span data-ttu-id="9f0f4-110">リソース ユーザー権限をローカルまたはドメイン グループ Microsoft SQL Server™ レベルを付与する場合は、追加し、管理の負担や総所有コストの削減、SQL Server で許可されるユーザー権限を変更することがなくサービス アカウントを減算します。</span><span class="sxs-lookup"><span data-stu-id="9f0f4-110">If you grant resource user rights to the local or domain group at the Microsoft SQL Server™ level, you can add and subtract service accounts without having to change the user rights granted in SQL Server, thus reducing your management burden and total cost of ownership.</span></span>  
  
  <span data-ttu-id="9f0f4-111">サービス アカウントが、ジョブの実行に必要な最小ユーザー権限を持っていることを確認するには、は、BizTalk サーバーのサービス アカウントを作成する SQL Server データベース ロールは、すべての BizTalk Server データベースで同一ではありません。</span><span class="sxs-lookup"><span data-stu-id="9f0f4-111">To ensure that the service accounts have the minimum user rights they need to do their jobs, the SQL Server Database roles that BizTalk Server creates for the service accounts are not identical on all the BizTalk Server databases.</span></span> <span data-ttu-id="9f0f4-112">管理および追跡データベースですべてのホスト インスタンス サービス アカウント必要があります、同じ SQL Server オブジェクトへのアクセスのため、BizTalk Server は BTS_Host_User という名前の 1 つの SQL Server データベース ロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="9f0f4-112">For the Management and Tracking databases, all of the host instance service accounts need access to the same SQL Server objects, so BizTalk Server created a single SQL Server Database role named BTS_Host_User.</span></span> <span data-ttu-id="9f0f4-113">BizTalk は、この SQL Server データベース ロールに BizTalk ホスト用に作成されたすべての Windows グループを追加します。</span><span class="sxs-lookup"><span data-stu-id="9f0f4-113">BizTalk adds all the Windows groups created for BizTalk hosts to this SQL Server Database role.</span></span>  
  
  <span data-ttu-id="9f0f4-114">メッセージ ボックス データベースの場合は、各ホストは専用のリソースの一部が。</span><span class="sxs-lookup"><span data-stu-id="9f0f4-114">For the MessageBox database, each host has some resources dedicated to that host.</span></span> <span data-ttu-id="9f0f4-115">BizTalk Server は、bts _ という名前のホストごとの SQL Server データベース ロールを作成します。\<*ホスト名*\>(_u)、1 つのアクセスをブロックするために、それぞれの SQL Server データベース ロールには、各ホストの Windows グループを追加します。別のホストのリソースをホストします。</span><span class="sxs-lookup"><span data-stu-id="9f0f4-115">BizTalk Server creates a SQL Server Database role per host, named BTS_\<*hostname*\>_User, and adds the Windows group for each host to its respective SQL Server Database role in order to block access of one host resources by another host.</span></span>  
  
## <a name="accounts-not-supported-by-biztalk-server"></a><span data-ttu-id="9f0f4-116">BizTalk Server でサポートされていないアカウント</span><span class="sxs-lookup"><span data-stu-id="9f0f4-116">Accounts not supported by BizTalk Server</span></span>  
 <span data-ttu-id="9f0f4-117">BizTalk Server では、次の組み込み Windows アカウントのいずれかを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="9f0f4-117">BizTalk Server does not support using any of the following built-in Windows accounts:</span></span>  
  
-   <span data-ttu-id="9f0f4-118">NT_AUTHORITY\NetworkService</span><span class="sxs-lookup"><span data-stu-id="9f0f4-118">NT_AUTHORITY\NetworkService</span></span>  
  
-   <span data-ttu-id="9f0f4-119">LocalSystem</span><span class="sxs-lookup"><span data-stu-id="9f0f4-119">LocalSystem</span></span>  
  
-   <span data-ttu-id="9f0f4-120">NT_AUTHORITY\LocalService</span><span class="sxs-lookup"><span data-stu-id="9f0f4-120">NT_AUTHORITY\LocalService</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f0f4-121">参照</span><span class="sxs-lookup"><span data-stu-id="9f0f4-121">See Also</span></span>  
 <span data-ttu-id="9f0f4-122">[管理ロールのアクセス制御](../core/access-control-for-administrative-roles.md) </span><span class="sxs-lookup"><span data-stu-id="9f0f4-122">[Access Control for Administrative Roles](../core/access-control-for-administrative-roles.md) </span></span>  
 <span data-ttu-id="9f0f4-123">[セキュリティ保護のための最小ユーザー権限](../core/minimum-security-user-rights.md) </span><span class="sxs-lookup"><span data-stu-id="9f0f4-123">[Minimum Security User Rights](../core/minimum-security-user-rights.md) </span></span>  
 <span data-ttu-id="9f0f4-124">[Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="9f0f4-124">[Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md) </span></span>  
 [<span data-ttu-id="9f0f4-125">アクセス制御とデータ セキュリティ</span><span class="sxs-lookup"><span data-stu-id="9f0f4-125">Access Control and Data Security</span></span>](../core/access-control-and-data-security.md)
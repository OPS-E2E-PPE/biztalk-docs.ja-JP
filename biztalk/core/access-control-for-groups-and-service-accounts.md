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
ms.openlocfilehash: da1bb9a52bef2e81729a8b566e4af4dcbed89c2a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021792"
---
# <a name="access-control-for-groups-and-service-accounts"></a><span data-ttu-id="f91d8-102">グループおよびサービス アカウントのアクセス制御</span><span class="sxs-lookup"><span data-stu-id="f91d8-102">Access Control for Groups and Service Accounts</span></span>
<span data-ttu-id="f91d8-103">BizTalk ホスト インスタンスは、ユーザーが作成したサービス アカウントで実行されます。</span><span class="sxs-lookup"><span data-stu-id="f91d8-103">Each BizTalk Host instance runs under a user-created service account.</span></span> <span data-ttu-id="f91d8-104">コンピュータにホスト インスタンスを作成するときには、サービス アカウントとパスワードを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f91d8-104">You must provide the service accounts and their passwords at the time you create the host instance on a computer.</span></span> <span data-ttu-id="f91d8-105">その後、BizTalk Server では、これらのサービス アカウントがローカルまたはドメインの Windows グループに追加され、次に、そのホストに固有の SQL Server データベース ロールに追加されます。これで、ジョブの実行に必要な最小限のユーザー権限がアカウントに許可されます。</span><span class="sxs-lookup"><span data-stu-id="f91d8-105">BizTalk Server then ensures that the accounts have the minimum user rights needed to do their jobs by adding each of these service accounts to a local or domain Windows group that, in turn, it adds to the SQL Server Database role specific to that host.</span></span>  
  
 <span data-ttu-id="f91d8-106">この方法には次の利点があります。</span><span class="sxs-lookup"><span data-stu-id="f91d8-106">This approach offers the following benefits:</span></span>  
  
- <span data-ttu-id="f91d8-107">ホスト インスタンスごとに異なるサービス アカウントを設定して、サーバーをオフラインにせずに各ホスト インスタンスのパスワードを変更できます。</span><span class="sxs-lookup"><span data-stu-id="f91d8-107">You can give each host instance a distinct service account, making it possible to change the passwords for each host instance without having to take servers offline.</span></span> <span data-ttu-id="f91d8-108">サービスを中断せずに、パスワード更新のロールを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f91d8-108">You can perform rolling password updates without interrupting service.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="f91d8-109">認証が信頼済みに設定されているホストと認証が信頼済みに設定されていないホストで、同じサービス アカウントを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="f91d8-109">You cannot use the same service account for hosts that are authentication trusted and hosts that are not authentication trusted.</span></span>  
  
- <span data-ttu-id="f91d8-110">リソース ユーザー権限を Microsoft SQL Server™ レベルでローカル グループまたはドメイン グループに許可すると、SQL Server で許可されているユーザー権限を変更することなくサービス アカウントの追加や削除を実行できるため、所有者の管理の負担や総コストが軽減されます。</span><span class="sxs-lookup"><span data-stu-id="f91d8-110">If you grant resource user rights to the local or domain group at the Microsoft SQL Server™ level, you can add and subtract service accounts without having to change the user rights granted in SQL Server, thus reducing your management burden and total cost of ownership.</span></span>  
  
  <span data-ttu-id="f91d8-111">サービス アカウントに対し、ジョブ実行に必要な最小限のユーザー権限が許可されるようにするため、BizTalk Server でサービス アカウントに作成される SQL Server データベース ロールは、すべての BizTalk Server データベースで重複しないようになっています。</span><span class="sxs-lookup"><span data-stu-id="f91d8-111">To ensure that the service accounts have the minimum user rights they need to do their jobs, the SQL Server Database roles that BizTalk Server creates for the service accounts are not identical on all the BizTalk Server databases.</span></span> <span data-ttu-id="f91d8-112">管理データベースおよび追跡データベースでは、ホスト インスタンス サービス アカウントはすべて同じ SQL Server オブジェクトにアクセスする必要があるため、BizTalk Server では BTS_Host_User という名前の単一の SQL Server データベース ロールが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f91d8-112">For the Management and Tracking databases, all of the host instance service accounts need access to the same SQL Server objects, so BizTalk Server created a single SQL Server Database role named BTS_Host_User.</span></span> <span data-ttu-id="f91d8-113">BizTalk ホスト用に作成された Windows グループは、すべてこの SQL Server データベース ロールに追加されます。</span><span class="sxs-lookup"><span data-stu-id="f91d8-113">BizTalk adds all the Windows groups created for BizTalk hosts to this SQL Server Database role.</span></span>  
  
  <span data-ttu-id="f91d8-114">メッセージ ボックス データベースでは、各ホストに専用のリソースが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="f91d8-114">For the MessageBox database, each host has some resources dedicated to that host.</span></span> <span data-ttu-id="f91d8-115">BizTalk Server は、bts _ という名前のホストごとの SQL Server データベース ロールを作成します。\<*ホスト名*\>(_u)、1 つのアクセスをブロックするために、それぞれの SQL Server データベース ロールには、各ホストの Windows グループを追加します。別のホストのリソースをホストします。</span><span class="sxs-lookup"><span data-stu-id="f91d8-115">BizTalk Server creates a SQL Server Database role per host, named BTS_\<*hostname*\>_User, and adds the Windows group for each host to its respective SQL Server Database role in order to block access of one host resources by another host.</span></span>  
  
## <a name="accounts-not-supported-by-biztalk-server"></a><span data-ttu-id="f91d8-116">BizTalk Server でサポートされていないアカウント</span><span class="sxs-lookup"><span data-stu-id="f91d8-116">Accounts not supported by BizTalk Server</span></span>  
 <span data-ttu-id="f91d8-117">BizTalk Server では、次の組み込み Windows アカウントの使用はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f91d8-117">BizTalk Server does not support using any of the following built-in Windows accounts:</span></span>  
  
-   <span data-ttu-id="f91d8-118">NT_AUTHORITY\NetworkService</span><span class="sxs-lookup"><span data-stu-id="f91d8-118">NT_AUTHORITY\NetworkService</span></span>  
  
-   <span data-ttu-id="f91d8-119">LocalSystem</span><span class="sxs-lookup"><span data-stu-id="f91d8-119">LocalSystem</span></span>  
  
-   <span data-ttu-id="f91d8-120">NT_AUTHORITY\LocalService</span><span class="sxs-lookup"><span data-stu-id="f91d8-120">NT_AUTHORITY\LocalService</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f91d8-121">参照</span><span class="sxs-lookup"><span data-stu-id="f91d8-121">See Also</span></span>  
 <span data-ttu-id="f91d8-122">[管理ロールのアクセス制御](../core/access-control-for-administrative-roles.md) </span><span class="sxs-lookup"><span data-stu-id="f91d8-122">[Access Control for Administrative Roles](../core/access-control-for-administrative-roles.md) </span></span>  
 <span data-ttu-id="f91d8-123">[セキュリティ保護のための最小ユーザー権限](../core/minimum-security-user-rights.md) </span><span class="sxs-lookup"><span data-stu-id="f91d8-123">[Minimum Security User Rights](../core/minimum-security-user-rights.md) </span></span>  
 <span data-ttu-id="f91d8-124">[Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="f91d8-124">[Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md) </span></span>  
 [<span data-ttu-id="f91d8-125">アクセス制御とデータ セキュリティ</span><span class="sxs-lookup"><span data-stu-id="f91d8-125">Access Control and Data Security</span></span>](../core/access-control-and-data-security.md)
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
# <a name="managing-hosts-and-service-accounts"></a><span data-ttu-id="0146f-102">ホストとサービス アカウントの管理</span><span class="sxs-lookup"><span data-stu-id="0146f-102">Managing Hosts and Service Accounts</span></span>
<span data-ttu-id="0146f-103">BizTalk Server の構成が済んだら、Windows グループおよびユーザー アカウントを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0146f-103">After you configure BizTalk Server, you must manage Windows groups and user accounts.</span></span> <span data-ttu-id="0146f-104">ここでは、BizTalk Server に必要なアカウントを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0146f-104">This section provides information about how to manage these accounts for BizTalk Server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0146f-105">BizTalk Server の複数サーバー環境では、ドメイン グローバル グループを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0146f-105">For a multiserver installation of BizTalk Server you must use a Domain Global group.</span></span> <span data-ttu-id="0146f-106">BizTalk Server の単一サーバー環境では、ドメイン グローバル グループを使用することも、ローカル グループを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="0146f-106">For a single server installation of BizTalk Server you can use either a Domain Global group or a local group.</span></span>  
  
 <span data-ttu-id="0146f-107">次のタスクは、Windows 管理者として実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0146f-107">You must be a Windows administrator to perform the following tasks:</span></span>  
  
- <span data-ttu-id="0146f-108">ホスト Windows グループを作成する</span><span class="sxs-lookup"><span data-stu-id="0146f-108">Create a host Windows group</span></span>  
  
- <span data-ttu-id="0146f-109">各ホスト インスタンスのサービス アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="0146f-109">Create service accounts for each host instance</span></span>  
  
- <span data-ttu-id="0146f-110">ホスト Windows グループにサービス アカウントを追加する</span><span class="sxs-lookup"><span data-stu-id="0146f-110">Add the service accounts to the host Windows group</span></span>  
  
- <span data-ttu-id="0146f-111">ホストに関連付けられている Windows グループに変更を加える</span><span class="sxs-lookup"><span data-stu-id="0146f-111">Modify the Windows group associated with the host</span></span>  
  
  <span data-ttu-id="0146f-112">完全な一覧と、グループと BizTalk Server でユーザー アカウントの説明では、[Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0146f-112">For a complete list and description of the groups and their affiliated user accounts in the BizTalk Server, see [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
  <span data-ttu-id="0146f-113">最低限のセキュリティ ユーザー権利の管理タスクの詳細については、[最小セキュリティ ユーザー権限](../core/minimum-security-user-rights.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0146f-113">For more information the minimum security user rights for administrative tasks, see [Minimum Security User Rights](../core/minimum-security-user-rights.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0146f-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="0146f-114">In This Section</span></span>  
  
-   [<span data-ttu-id="0146f-115">新しいホストとホスト インスタンスのアカウントをサービスを作成する方法</span><span class="sxs-lookup"><span data-stu-id="0146f-115">How to Create Service Accounts for New Hosts and Host Instances</span></span>](../core/how-to-create-service-accounts-for-new-hosts-and-host-instances.md)  
  
-   [<span data-ttu-id="0146f-116">サービス アカウントとパスワードを変更する方法</span><span class="sxs-lookup"><span data-stu-id="0146f-116">How to Change Service Accounts and Passwords</span></span>](../core/how-to-change-service-accounts-and-passwords.md)
---
title: Windows グループとユーザー アカウントを管理するためのベスト プラクティス |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- best practices, Windows groups
- authenticating, best practices
- Windows groups, security
- best practices, user accounts
- best practices, security
- security, best practices
- user accounts, security
- authenticating, security
- Windows groups, best practices
- best practices, authenticating
- user accounts, best practices
- hosts, security
- hosts, best practices
- best practices, hosts
ms.assetid: 0c4a141e-97ce-434a-8e45-a56c634bbd6c
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 71f7560e3867bf290f20e0f2f49a740d7298131b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231226"
---
# <a name="best-practices-for-managing-windows-groups-and-user-accounts"></a><span data-ttu-id="0ec2d-102">Windows グループおよびユーザー アカウントの管理のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="0ec2d-102">Best Practices for Managing Windows Groups and User Accounts</span></span>
<span data-ttu-id="0ec2d-103">このセクションでは、Windows グループおよびユーザー アカウントのセキュリティ管理のベスト プラクティスおよびヒントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="0ec2d-103">This section contains best practices and tips for managing security for Windows groups and user accounts.</span></span>  
  
-   <span data-ttu-id="0ec2d-104">**サービス アカウントのホスト インスタンスに必要な最低限の特権を使用します。**</span><span class="sxs-lookup"><span data-stu-id="0ec2d-104">**Use service accounts with minimum privileges necessary for host instances**</span></span>  
  
     <span data-ttu-id="0ec2d-105">BizTalk Server 環境のセキュリティを確保するには、ホスト インスタンスの実行に必要な最小限の権限を持つサービス アカウントを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0ec2d-105">To help ensure the security of your BizTalk Server environment, we recommend that you use service accounts with the minimum privileges necessary to run host instances.</span></span> <span data-ttu-id="0ec2d-106">サービス アカウントに必要な最低限の特権の詳細については、次を参照してください。[アクセス制御とデータ セキュリティ](../core/access-control-and-data-security.md)です。</span><span class="sxs-lookup"><span data-stu-id="0ec2d-106">For more information about the minimum privileges that service accounts require, see [Access Control and Data Security](../core/access-control-and-data-security.md).</span></span>  
  
-   <span data-ttu-id="0ec2d-107">**信頼されている認証および信頼されていないホストに別のユーザー グループを使用します。**</span><span class="sxs-lookup"><span data-stu-id="0ec2d-107">**Use different user groups for authentication trusted and non-trusted hosts**</span></span>  
  
     <span data-ttu-id="0ec2d-108">信頼されていない認証ホストの権限が、信頼済み認証ホストの権限よりも低くなるように、各ホストに別々のサービス アカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ec2d-108">To ensure that non-authentication trusted hosts have fewer privileges than authentication trusted hosts, you must use different service accounts for each host.</span></span>  
  
-   <span data-ttu-id="0ec2d-109">**各 BizTalk ホストの別のユーザー グループを使用します。**</span><span class="sxs-lookup"><span data-stu-id="0ec2d-109">**Use a different user group for each BizTalk Host**</span></span>  
  
     <span data-ttu-id="0ec2d-110">ホスト間のセキュリティ境界を最大限に高めるには、BizTalk グループ内の各 BizTalk ホストに対して、別々の Windows ユーザー グループを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0ec2d-110">To maximize the security boundary between hosts, we recommend that you use a different Windows user group for each BizTalk Host in your BizTalk group.</span></span>  
  
-   <span data-ttu-id="0ec2d-111">**BizTalk Server 管理者グループからインストール ユーザーを削除します。**</span><span class="sxs-lookup"><span data-stu-id="0ec2d-111">**Remove the installation user from the BizTalk Server Administrators group**</span></span>  
  
     <span data-ttu-id="0ec2d-112">複数のローカル グループがある 1 台のコンピュータに BizTalk Server をインストールすると、BizTalk Server の対話型インストールを実行しているユーザーは、BizTalk Server 管理者グループに自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="0ec2d-112">When you install BizTalk Server on a single computer with local groups, the user performing an interactive installation of BizTalk Server is automatically added to the BizTalk Server Administrators group.</span></span> <span data-ttu-id="0ec2d-113">これによりユーザーは、構成マネージャで BizTalk Server を構成できます。</span><span class="sxs-lookup"><span data-stu-id="0ec2d-113">This allows that user to configure BizTalk Server with the Configuration Manager.</span></span>  
  
     <span data-ttu-id="0ec2d-114">BizTalk Server をインストールしたユーザーが BizTalk Server の管理担当ではない場合、BizTalk Server を構成した後で、このユーザーを BizTalk Server 管理者グループから削除することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0ec2d-114">If the user who installs BizTalk Server will not be administering BizTalk Server, we recommend that you remove this user from the BizTalk Server Administrators group after BizTalk Server is configured.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ec2d-115">参照</span><span class="sxs-lookup"><span data-stu-id="0ec2d-115">See Also</span></span>  
 [<span data-ttu-id="0ec2d-116">BizTalk Server のセキュリティを管理します。</span><span class="sxs-lookup"><span data-stu-id="0ec2d-116">Managing BizTalk Server Security</span></span>](../core/managing-biztalk-server-security.md)
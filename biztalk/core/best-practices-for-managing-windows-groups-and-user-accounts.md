---
title: Windows グループとユーザー アカウントを管理するためのベスト プラクティス |Microsoft Docs
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
ms.openlocfilehash: 6720135f15b2c6d50bb193cd6e533e5b06f71961
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358202"
---
# <a name="best-practices-for-managing-windows-groups-and-user-accounts"></a><span data-ttu-id="af112-102">Windows グループとユーザー アカウントを管理するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="af112-102">Best Practices for Managing Windows Groups and User Accounts</span></span>
<span data-ttu-id="af112-103">このセクションには、ベスト プラクティスや Windows グループとユーザー アカウントのセキュリティを管理するためのヒントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="af112-103">This section contains best practices and tips for managing security for Windows groups and user accounts.</span></span>  
  
-   <span data-ttu-id="af112-104">**ホスト インスタンスに必要な最小限の特権を使用してサービス アカウント**</span><span class="sxs-lookup"><span data-stu-id="af112-104">**Use service accounts with minimum privileges necessary for host instances**</span></span>  
  
     <span data-ttu-id="af112-105">BizTalk Server 環境のセキュリティを確保するには、ホスト インスタンスを実行するために必要な最小限の特権をサービス アカウントを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="af112-105">To help ensure the security of your BizTalk Server environment, we recommend that you use service accounts with the minimum privileges necessary to run host instances.</span></span> <span data-ttu-id="af112-106">サービス アカウントに必要な最低限の特権の詳細については、次を参照してください。[アクセス制御とデータ セキュリティ](../core/access-control-and-data-security.md)します。</span><span class="sxs-lookup"><span data-stu-id="af112-106">For more information about the minimum privileges that service accounts require, see [Access Control and Data Security](../core/access-control-and-data-security.md).</span></span>  
  
-   <span data-ttu-id="af112-107">**信頼された認証と信頼されていないホストの別のユーザー グループを使用します。**</span><span class="sxs-lookup"><span data-stu-id="af112-107">**Use different user groups for authentication trusted and non-trusted hosts**</span></span>  
  
     <span data-ttu-id="af112-108">ホストが信頼されたホストの認証よりも少ない特権を持つその非認証が信頼されていることを確認するには、ホストごとに異なるサービス アカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af112-108">To ensure that non-authentication trusted hosts have fewer privileges than authentication trusted hosts, you must use different service accounts for each host.</span></span>  
  
-   <span data-ttu-id="af112-109">**各 BizTalk ホストの別のユーザーのグループを使用します。**</span><span class="sxs-lookup"><span data-stu-id="af112-109">**Use a different user group for each BizTalk Host**</span></span>  
  
     <span data-ttu-id="af112-110">ホスト間のセキュリティ境界を最大化するには、BizTalk グループで、各 BizTalk ホストの別の Windows ユーザー グループを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="af112-110">To maximize the security boundary between hosts, we recommend that you use a different Windows user group for each BizTalk Host in your BizTalk group.</span></span>  
  
-   <span data-ttu-id="af112-111">**BizTalk Server 管理者グループからのインストール ユーザーを削除します。**</span><span class="sxs-lookup"><span data-stu-id="af112-111">**Remove the installation user from the BizTalk Server Administrators group**</span></span>  
  
     <span data-ttu-id="af112-112">ローカル グループを含む 1 台のコンピューターに BizTalk Server をインストールすると、BizTalk Server の対話型インストールを実行するユーザーは、BizTalk Server 管理者グループに自動的に追加します。</span><span class="sxs-lookup"><span data-stu-id="af112-112">When you install BizTalk Server on a single computer with local groups, the user performing an interactive installation of BizTalk Server is automatically added to the BizTalk Server Administrators group.</span></span> <span data-ttu-id="af112-113">これにより、Configuration Manager での BizTalk Server を構成するには、そのユーザーができます。</span><span class="sxs-lookup"><span data-stu-id="af112-113">This allows that user to configure BizTalk Server with the Configuration Manager.</span></span>  
  
     <span data-ttu-id="af112-114">BizTalk Server をインストールしたユーザーには BizTalk Server が管理するされない場合、は、BizTalk Server を構成した後、このユーザーを BizTalk Server 管理者グループから削除することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="af112-114">If the user who installs BizTalk Server will not be administering BizTalk Server, we recommend that you remove this user from the BizTalk Server Administrators group after BizTalk Server is configured.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af112-115">参照</span><span class="sxs-lookup"><span data-stu-id="af112-115">See Also</span></span>  
 [<span data-ttu-id="af112-116">BizTalk Server のセキュリティの管理</span><span class="sxs-lookup"><span data-stu-id="af112-116">Managing BizTalk Server Security</span></span>](../core/managing-biztalk-server-security.md)
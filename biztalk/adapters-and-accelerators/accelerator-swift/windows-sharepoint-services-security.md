---
title: Windows SharePoint Services のセキュリティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, Windows SharePoint Services
- Windows SharePoint Services, security
- security, BAS
- BAS, security
ms.assetid: ada6abd3-b867-49a6-8ee0-1466adc87dc5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0979e0a7c75cf3f1450500253569fc47b3dae8b7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376900"
---
# <a name="windows-sharepoint-services-security"></a><span data-ttu-id="3140a-102">Windows SharePoint Services のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="3140a-102">Windows SharePoint Services Security</span></span>
<span data-ttu-id="3140a-103">Windows SharePoint Services 3.0 では、Windows SharePoint Services サイト グループを使用して、サイト全体のセキュリティを管理します。</span><span class="sxs-lookup"><span data-stu-id="3140a-103">Windows SharePoint Services 3.0 uses Windows SharePoint Services site groups to manage site-wide security.</span></span> <span data-ttu-id="3140a-104">各サイトのグループは、対応する権限を持ちます。</span><span class="sxs-lookup"><span data-stu-id="3140a-104">Each site group possesses corresponding rights.</span></span> <span data-ttu-id="3140a-105">権限は、ユーザーが実行できるアクションをなどの表示など、編集、およびサイトのリソースを削除します。</span><span class="sxs-lookup"><span data-stu-id="3140a-105">Rights are actions that users can perform—such as view, edit, and delete site resources.</span></span> <span data-ttu-id="3140a-106">リソースには、サイトのリスト、ドキュメント ライブラリ、およびサイトの管理が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3140a-106">Resources include site lists, document libraries, and site administration.</span></span> <span data-ttu-id="3140a-107">各ロールを作成するには、各リソースをグループ化するには、Windows SharePoint サービス サイト グループを定義し、それに応じて権利を割り当てる必要がありますのプロファイル Web クライアントでのアクセスを持っています。</span><span class="sxs-lookup"><span data-stu-id="3140a-107">For each role created in the Profile Web Client you need to define a Windows SharePoint Service site group and assign rights accordingly to each resource to which that group has access.</span></span>  
  
 <span data-ttu-id="3140a-108">WSS 3.0 のセキュリティの詳細については、WSS 3.0 の評価ガイドを参照してください。 [ http://go.microsoft.com/fwlink/?LinkID=94370](http://go.microsoft.com/fwlink/?LinkID=94370)します。</span><span class="sxs-lookup"><span data-stu-id="3140a-108">For more information about WSS 3.0 security, see the WSS 3.0 evaluation guide at [http://go.microsoft.com/fwlink/?LinkID=94370](http://go.microsoft.com/fwlink/?LinkID=94370).</span></span>  
  
 <span data-ttu-id="3140a-109">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3140a-109">This section contains:</span></span>  
  
-   [<span data-ttu-id="3140a-110">A4SWIFT ユーザーの構成</span><span class="sxs-lookup"><span data-stu-id="3140a-110">Configuring A4SWIFT Users</span></span>](../../adapters-and-accelerators/accelerator-swift/configuring-a4swift-users.md)  
  
-   [<span data-ttu-id="3140a-111">A4SWIFT サイト グループの構成</span><span class="sxs-lookup"><span data-stu-id="3140a-111">Configuring A4SWIFT Site Groups</span></span>](../../adapters-and-accelerators/accelerator-swift/configuring-a4swift-site-groups.md)  
  
-   [<span data-ttu-id="3140a-112">権限の割り当て</span><span class="sxs-lookup"><span data-stu-id="3140a-112">Assigning Rights</span></span>](../../adapters-and-accelerators/accelerator-swift/assigning-rights.md)
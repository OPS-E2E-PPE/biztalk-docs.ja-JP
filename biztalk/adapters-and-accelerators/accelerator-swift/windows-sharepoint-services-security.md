---
title: Windows SharePoint Services のセキュリティ |Microsoft ドキュメント
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
ms.openlocfilehash: 184f5a237f796eac69de6c481e69a87a4a5358df
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214490"
---
# <a name="windows-sharepoint-services-security"></a><span data-ttu-id="29494-102">Windows SharePoint Services のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="29494-102">Windows SharePoint Services Security</span></span>
<span data-ttu-id="29494-103">Windows SharePoint Services 3.0 は、サイト全体のセキュリティを管理するのに Windows SharePoint Services サイト グループを使用します。</span><span class="sxs-lookup"><span data-stu-id="29494-103">Windows SharePoint Services 3.0 uses Windows SharePoint Services site groups to manage site-wide security.</span></span> <span data-ttu-id="29494-104">各サイト グループでは、対応する権限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="29494-104">Each site group possesses corresponding rights.</span></span> <span data-ttu-id="29494-105">権限とはユーザーが実行できる操作などの表示など、編集、およびサイトのリソースを削除します。</span><span class="sxs-lookup"><span data-stu-id="29494-105">Rights are actions that users can perform—such as view, edit, and delete site resources.</span></span> <span data-ttu-id="29494-106">リソースには、サイトのリスト、ドキュメント ライブラリ、およびサイトの管理が含まれます。</span><span class="sxs-lookup"><span data-stu-id="29494-106">Resources include site lists, document libraries, and site administration.</span></span> <span data-ttu-id="29494-107">プロファイルする Web クライアントを Windows SharePoint サービス サイト グループを定義し、それに応じて権利を割り当てる必要があるには、各リソースにグループ化で作成された各ロールにアクセスしています。</span><span class="sxs-lookup"><span data-stu-id="29494-107">For each role created in the Profile Web Client you need to define a Windows SharePoint Service site group and assign rights accordingly to each resource to which that group has access.</span></span>  
  
 <span data-ttu-id="29494-108">WSS 3.0 セキュリティの詳細については、WSS 3.0 の評価ガイドを参照してください。 [http://go.microsoft.com/fwlink/?LinkID=94370](http://go.microsoft.com/fwlink/?LinkID=94370)です。</span><span class="sxs-lookup"><span data-stu-id="29494-108">For more information about WSS 3.0 security, see the WSS 3.0 evaluation guide at [http://go.microsoft.com/fwlink/?LinkID=94370](http://go.microsoft.com/fwlink/?LinkID=94370).</span></span>  
  
 <span data-ttu-id="29494-109">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="29494-109">This section contains:</span></span>  
  
-   [<span data-ttu-id="29494-110">A4SWIFT のユーザーを構成します。</span><span class="sxs-lookup"><span data-stu-id="29494-110">Configuring A4SWIFT Users</span></span>](../../adapters-and-accelerators/accelerator-swift/configuring-a4swift-users.md)  
  
-   [<span data-ttu-id="29494-111">A4SWIFT サイト グループの構成</span><span class="sxs-lookup"><span data-stu-id="29494-111">Configuring A4SWIFT Site Groups</span></span>](../../adapters-and-accelerators/accelerator-swift/configuring-a4swift-site-groups.md)  
  
-   [<span data-ttu-id="29494-112">権利の割り当てください。</span><span class="sxs-lookup"><span data-stu-id="29494-112">Assigning Rights</span></span>](../../adapters-and-accelerators/accelerator-swift/assigning-rights.md)
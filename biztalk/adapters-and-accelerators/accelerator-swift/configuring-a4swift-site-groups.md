---
title: A4SWIFT サイト グループの構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- site groups, creating
- creating, site groups
- security, user accounts
- user accounts, site groups
- site groups, user accounts
ms.assetid: ec2f3efe-439a-4018-ad94-5ab0fb2808ee
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0070f10819ebbde18cdeab9c3bd534ca74bfbcd9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209010"
---
# <a name="configuring-a4swift-site-groups"></a><span data-ttu-id="a9435-102">A4SWIFT サイト グループの構成</span><span class="sxs-lookup"><span data-stu-id="a9435-102">Configuring A4SWIFT Site Groups</span></span>
<span data-ttu-id="a9435-103">Message Repair and New Submission の構成時に作成されたドキュメント ライブラリのアクセス許可をロックダウンする対応するサイト グループを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9435-103">You need to create the corresponding site groups to lock down the permissions on the document libraries created during Message Repair and New Submission configuration.</span></span> <span data-ttu-id="a9435-104">前のセクションの例のように、A4SWIFT 管理者は MRSR サイトに移動して、次のサイト グループを設定します。</span><span class="sxs-lookup"><span data-stu-id="a9435-104">To do so with the example in the preceding section, an A4SWIFT Administrator would go to the MRSR site and set up the following site groups:</span></span>  
  
-   <span data-ttu-id="a9435-105">Payments_Creators</span><span class="sxs-lookup"><span data-stu-id="a9435-105">Payments_Creators</span></span>  
  
-   <span data-ttu-id="a9435-106">Payments_Repairers</span><span class="sxs-lookup"><span data-stu-id="a9435-106">Payments_Repairers</span></span>  
  
-   <span data-ttu-id="a9435-107">Payments_Approvers</span><span class="sxs-lookup"><span data-stu-id="a9435-107">Payments_Approvers</span></span>  
  
 <span data-ttu-id="a9435-108">これらのサイト グループの列ごとには、次のアクセス許可を適用してください。</span><span class="sxs-lookup"><span data-stu-id="a9435-108">For each of these site groups the following permissions should be applied:</span></span>  
  
-   <span data-ttu-id="a9435-109">**項目を表示します。**</span><span class="sxs-lookup"><span data-stu-id="a9435-109">**View Items.**</span></span> <span data-ttu-id="a9435-110">ドキュメント ライブラリのドキュメント、リストの項目を表示では、Web ディスカッションのコメントを表示し、リストの電子メール通知を設定します。</span><span class="sxs-lookup"><span data-stu-id="a9435-110">View items in lists, documents in document libraries, view Web discussion comments, and set up e-mail alerts for lists.</span></span>  
  
-   <span data-ttu-id="a9435-111">**ページを表示します。**</span><span class="sxs-lookup"><span data-stu-id="a9435-111">**View Pages.**</span></span> <span data-ttu-id="a9435-112">Web サイト内のページを表示します。</span><span class="sxs-lookup"><span data-stu-id="a9435-112">View pages in a Web site.</span></span>  
  
 <span data-ttu-id="a9435-113">各ユーザーの支払い部門では、役割に参加している、する必要があります、新しいサイトのユーザーを作成し、そのユーザーに対応するサイト グループを割り当てます[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]MMC の構成時に作成されたロールです。</span><span class="sxs-lookup"><span data-stu-id="a9435-113">For each user who participates in the roles for the Payments department, you need to create a new site user and assign that user to the site group that corresponds to [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] roles created during MMC configuration.</span></span>
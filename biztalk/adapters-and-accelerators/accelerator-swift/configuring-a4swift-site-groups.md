---
title: A4SWIFT サイト グループの構成 |Microsoft Docs
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
ms.openlocfilehash: e56eb836ffde957244b5ca80e6d7491f9e8c207c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378955"
---
# <a name="configuring-a4swift-site-groups"></a><span data-ttu-id="9a583-102">A4SWIFT サイト グループの構成</span><span class="sxs-lookup"><span data-stu-id="9a583-102">Configuring A4SWIFT Site Groups</span></span>
<span data-ttu-id="9a583-103">Message Repair and New Submission の構成時に作成されたドキュメント ライブラリのアクセス許可をロックダウンする対応するサイトのグループを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a583-103">You need to create the corresponding site groups to lock down the permissions on the document libraries created during Message Repair and New Submission configuration.</span></span> <span data-ttu-id="9a583-104">前のセクションの例のように、A4SWIFT 管理者は MRSR サイトに移動して、次のサイト グループを設定します。</span><span class="sxs-lookup"><span data-stu-id="9a583-104">To do so with the example in the preceding section, an A4SWIFT Administrator would go to the MRSR site and set up the following site groups:</span></span>  
  
- <span data-ttu-id="9a583-105">Payments_Creators</span><span class="sxs-lookup"><span data-stu-id="9a583-105">Payments_Creators</span></span>  
  
- <span data-ttu-id="9a583-106">Payments_Repairers</span><span class="sxs-lookup"><span data-stu-id="9a583-106">Payments_Repairers</span></span>  
  
- <span data-ttu-id="9a583-107">Payments_Approvers</span><span class="sxs-lookup"><span data-stu-id="9a583-107">Payments_Approvers</span></span>  
  
  <span data-ttu-id="9a583-108">これらのサイト グループごとには、次のアクセス許可を適用してください。</span><span class="sxs-lookup"><span data-stu-id="9a583-108">For each of these site groups the following permissions should be applied:</span></span>  
  
- <span data-ttu-id="9a583-109">**項目を表示します。**</span><span class="sxs-lookup"><span data-stu-id="9a583-109">**View Items.**</span></span> <span data-ttu-id="9a583-110">リスト、ドキュメント ライブラリにアイテムを表示、Web ディスカッション コメントを表示およびリストの電子メール通知を設定します。</span><span class="sxs-lookup"><span data-stu-id="9a583-110">View items in lists, documents in document libraries, view Web discussion comments, and set up e-mail alerts for lists.</span></span>  
  
- <span data-ttu-id="9a583-111">**ページを表示します。**</span><span class="sxs-lookup"><span data-stu-id="9a583-111">**View Pages.**</span></span> <span data-ttu-id="9a583-112">Web サイトでページを表示します。</span><span class="sxs-lookup"><span data-stu-id="9a583-112">View pages in a Web site.</span></span>  
  
  <span data-ttu-id="9a583-113">支払部門のロールに参加しているユーザーごとに、新しいサイトのユーザーを作成し、そのユーザーに対応するサイトのグループに割り当てする必要があります。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] MMC 構成中に作成されたロール。</span><span class="sxs-lookup"><span data-stu-id="9a583-113">For each user who participates in the roles for the Payments department, you need to create a new site user and assign that user to the site group that corresponds to [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] roles created during MMC configuration.</span></span>
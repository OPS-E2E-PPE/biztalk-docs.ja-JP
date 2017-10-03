---
title: "A4SWIFT のユーザーの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, user accounts
- creating, user accounts
- user accounts, creating
ms.assetid: 45dcbece-ec8d-410a-8320-79bfbc4c779d
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79c3b63cd77bb34545f4c4093796310aa7720563
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-a4swift-users"></a><span data-ttu-id="4cb03-102">A4SWIFT のユーザーを構成します。</span><span class="sxs-lookup"><span data-stu-id="4cb03-102">Configuring A4SWIFT Users</span></span>
<span data-ttu-id="4cb03-103">インストール中に[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]、A4SWIFT 構成プログラムが既定の取引パートナー プロファイルやアグリーメントが作成され、BizTalk Server を登録します。</span><span class="sxs-lookup"><span data-stu-id="4cb03-103">During installation of [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)], the A4SWIFT configuration program creates default trading partner profiles and agreements, and registers the BizTalk Server.</span></span> <span data-ttu-id="4cb03-104">A4SWIFT には、Message Repair and New Submission のコンポーネントで使用されるドキュメント ライブラリも作成されます。</span><span class="sxs-lookup"><span data-stu-id="4cb03-104">A4SWIFT also creates document libraries used by the Message Repair and New Submission component.</span></span>  
  
 <span data-ttu-id="4cb03-105">A4SWIFT のインストール時に、次のドキュメント フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="4cb03-105">A4SWIFT creates the following document folders during installation:</span></span>  
  
-   <span data-ttu-id="4cb03-106">送信トレイ ドキュメント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="4cb03-106">Outbox document library</span></span>  
  
-   <span data-ttu-id="4cb03-107">テンプレート ドキュメント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="4cb03-107">Templates document library</span></span>  
  
-   <span data-ttu-id="4cb03-108">未解析のドキュメント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="4cb03-108">Unparsed document library</span></span>  
  
-   <span data-ttu-id="4cb03-109">新しい SWIFT MT メッセージ ドキュメント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="4cb03-109">New SWIFT MT Message document library</span></span>  
  
-   <span data-ttu-id="4cb03-110">新しい SWIFT MX メッセージ ドキュメント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="4cb03-110">New SWIFT MX Messages document library</span></span>  
  
 <span data-ttu-id="4cb03-111">各部署を作成すると、A4SWIFT 管理者は、対応する部門のグループをサイトを手動で設定する必要があり、A4SWIFT がロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="4cb03-111">For each department created, the A4SWIFT Administrator must manually set up site groups for the corresponding departments and A4SWIFT defined roles.</span></span> <span data-ttu-id="4cb03-112">各部門/ロールには、受信トレイ プロファイル Web Client(PWC) によって自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="4cb03-112">Each department/role has an inbox created automatically by the Profile Web Client(PWC).</span></span>  
  
 <span data-ttu-id="4cb03-113">A4SWIFT セットアップ構成プログラムが完了した後、A4SWIFT 管理者は、組織の各部門のワークフローを構成します。</span><span class="sxs-lookup"><span data-stu-id="4cb03-113">After the A4SWIFT setup configuration program is completed, the A4SWIFT Administrator configures workflows for each department in the organization.</span></span> <span data-ttu-id="4cb03-114">プロファイル Web クライアントを通じて、Message Repair and New Submission の構成時に、対応する受信トレイは、部門またはロールの組み合わせごとに作成されます。</span><span class="sxs-lookup"><span data-stu-id="4cb03-114">During Message Repair and New Submission configuration, through the Profile Web Client, corresponding inboxes are created for each department/role combination.</span></span> <span data-ttu-id="4cb03-115">など、PWC 構成中に、A4SWIFT 管理者は支払いをという名前の部門を作成し、し、支払と呼ばれる部門に作成者、Repairers、および承認者の役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4cb03-115">For example, during PWC configuration an A4SWIFT Administrator creates a department named Payments and then assigns the roles of Creators, Repairers, and Approvers to a department called Payments.</span></span> <span data-ttu-id="4cb03-116">MRSR サイト上のドキュメント ライブラリは、次の表の例に示すように、受信トレイ名で作成されます。</span><span class="sxs-lookup"><span data-stu-id="4cb03-116">Document libraries on the MRSR site are created with the inbox names as shown in the examples in the following table:</span></span>  
  
|<span data-ttu-id="4cb03-117">部門名</span><span class="sxs-lookup"><span data-stu-id="4cb03-117">Department name</span></span>|<span data-ttu-id="4cb03-118">ロール名</span><span class="sxs-lookup"><span data-stu-id="4cb03-118">Role name</span></span>|<span data-ttu-id="4cb03-119">受信トレイ名</span><span class="sxs-lookup"><span data-stu-id="4cb03-119">Inbox name</span></span>|  
|---------------------|---------------|----------------|  
|<span data-ttu-id="4cb03-120">支払い</span><span class="sxs-lookup"><span data-stu-id="4cb03-120">Payments</span></span>|<span data-ttu-id="4cb03-121">作成者</span><span class="sxs-lookup"><span data-stu-id="4cb03-121">Creators</span></span>|<span data-ttu-id="4cb03-122">Payments_Creator</span><span class="sxs-lookup"><span data-stu-id="4cb03-122">Payments_Creator</span></span>|  
|<span data-ttu-id="4cb03-123">支払い</span><span class="sxs-lookup"><span data-stu-id="4cb03-123">Payments</span></span>|<span data-ttu-id="4cb03-124">Repairers</span><span class="sxs-lookup"><span data-stu-id="4cb03-124">Repairers</span></span>|<span data-ttu-id="4cb03-125">Payments_Repairers</span><span class="sxs-lookup"><span data-stu-id="4cb03-125">Payments_Repairers</span></span>|  
|<span data-ttu-id="4cb03-126">支払い</span><span class="sxs-lookup"><span data-stu-id="4cb03-126">Payments</span></span>|<span data-ttu-id="4cb03-127">承認者</span><span class="sxs-lookup"><span data-stu-id="4cb03-127">Approvers</span></span>|<span data-ttu-id="4cb03-128">Payments_Approvers</span><span class="sxs-lookup"><span data-stu-id="4cb03-128">Payments_Approvers</span></span>|
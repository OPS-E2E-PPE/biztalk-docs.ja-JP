---
title: A4SWIFT ユーザーの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, user accounts
- creating, user accounts
- user accounts, creating
ms.assetid: 45dcbece-ec8d-410a-8320-79bfbc4c779d
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b75a3e95c836f8a577543b43319e6abe49a96c42
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005259"
---
# <a name="configuring-a4swift-users"></a><span data-ttu-id="395bf-102">A4SWIFT ユーザーの構成</span><span class="sxs-lookup"><span data-stu-id="395bf-102">Configuring A4SWIFT Users</span></span>
<span data-ttu-id="395bf-103">インストール中に[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]、A4SWIFT 構成プログラムが既定取引先のプロファイルと、契約を作成し、BizTalk Server を登録します。</span><span class="sxs-lookup"><span data-stu-id="395bf-103">During installation of [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)], the A4SWIFT configuration program creates default trading partner profiles and agreements, and registers the BizTalk Server.</span></span> <span data-ttu-id="395bf-104">また、A4SWIFT には、Message Repair and New Submission のコンポーネントで使用されるドキュメント ライブラリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="395bf-104">A4SWIFT also creates document libraries used by the Message Repair and New Submission component.</span></span>  
  
 <span data-ttu-id="395bf-105">A4SWIFT のインストール中に次のドキュメント フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="395bf-105">A4SWIFT creates the following document folders during installation:</span></span>  
  
- <span data-ttu-id="395bf-106">送信トレイ ドキュメント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="395bf-106">Outbox document library</span></span>  
  
- <span data-ttu-id="395bf-107">テンプレート ドキュメント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="395bf-107">Templates document library</span></span>  
  
- <span data-ttu-id="395bf-108">未解析のドキュメント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="395bf-108">Unparsed document library</span></span>  
  
- <span data-ttu-id="395bf-109">新しい SWIFT MT メッセージ ドキュメント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="395bf-109">New SWIFT MT Message document library</span></span>  
  
- <span data-ttu-id="395bf-110">新しい SWIFT MX メッセージ ドキュメント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="395bf-110">New SWIFT MX Messages document library</span></span>  
  
  <span data-ttu-id="395bf-111">各部門を作成すると、A4SWIFT 管理者は、対応する部門のサイト グループを手動で設定する必要があり、A4SWIFT がロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="395bf-111">For each department created, the A4SWIFT Administrator must manually set up site groups for the corresponding departments and A4SWIFT defined roles.</span></span> <span data-ttu-id="395bf-112">各部門/ロールでは、プロファイルの Web Client(PWC) によって自動的に作成された受信トレイがあります。</span><span class="sxs-lookup"><span data-stu-id="395bf-112">Each department/role has an inbox created automatically by the Profile Web Client(PWC).</span></span>  
  
  <span data-ttu-id="395bf-113">A4SWIFT セットアップ構成プログラムが完了した後、A4SWIFT 管理者は、組織の各部門のワークフローを構成します。</span><span class="sxs-lookup"><span data-stu-id="395bf-113">After the A4SWIFT setup configuration program is completed, the A4SWIFT Administrator configures workflows for each department in the organization.</span></span> <span data-ttu-id="395bf-114">プロファイル Web クライアントを通じて、Message Repair and New Submission の構成中に、対応する受信トレイは、部門/ロールの組み合わせごとに作成されます。</span><span class="sxs-lookup"><span data-stu-id="395bf-114">During Message Repair and New Submission configuration, through the Profile Web Client, corresponding inboxes are created for each department/role combination.</span></span> <span data-ttu-id="395bf-115">たとえば、PWC 構成中に、A4SWIFT 管理者は支払いをという名前の部署を作成しますを支払いと呼ばれる部門に作成者、Repairers、および承認者のロールを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="395bf-115">For example, during PWC configuration an A4SWIFT Administrator creates a department named Payments and then assigns the roles of Creators, Repairers, and Approvers to a department called Payments.</span></span> <span data-ttu-id="395bf-116">MRSR サイトのドキュメント ライブラリは、次の表の例で示すように、受信トレイの名前で作成されます。</span><span class="sxs-lookup"><span data-stu-id="395bf-116">Document libraries on the MRSR site are created with the inbox names as shown in the examples in the following table:</span></span>  
  
|<span data-ttu-id="395bf-117">部門名</span><span class="sxs-lookup"><span data-stu-id="395bf-117">Department name</span></span>|<span data-ttu-id="395bf-118">ロール名</span><span class="sxs-lookup"><span data-stu-id="395bf-118">Role name</span></span>|<span data-ttu-id="395bf-119">受信トレイ名</span><span class="sxs-lookup"><span data-stu-id="395bf-119">Inbox name</span></span>|  
|---------------------|---------------|----------------|  
|<span data-ttu-id="395bf-120">支払い</span><span class="sxs-lookup"><span data-stu-id="395bf-120">Payments</span></span>|<span data-ttu-id="395bf-121">作成者</span><span class="sxs-lookup"><span data-stu-id="395bf-121">Creators</span></span>|<span data-ttu-id="395bf-122">Payments_Creator</span><span class="sxs-lookup"><span data-stu-id="395bf-122">Payments_Creator</span></span>|  
|<span data-ttu-id="395bf-123">支払い</span><span class="sxs-lookup"><span data-stu-id="395bf-123">Payments</span></span>|<span data-ttu-id="395bf-124">Repairers</span><span class="sxs-lookup"><span data-stu-id="395bf-124">Repairers</span></span>|<span data-ttu-id="395bf-125">Payments_Repairers</span><span class="sxs-lookup"><span data-stu-id="395bf-125">Payments_Repairers</span></span>|  
|<span data-ttu-id="395bf-126">支払い</span><span class="sxs-lookup"><span data-stu-id="395bf-126">Payments</span></span>|<span data-ttu-id="395bf-127">承認者</span><span class="sxs-lookup"><span data-stu-id="395bf-127">Approvers</span></span>|<span data-ttu-id="395bf-128">Payments_Approvers</span><span class="sxs-lookup"><span data-stu-id="395bf-128">Payments_Approvers</span></span>|
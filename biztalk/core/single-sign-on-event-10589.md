---
title: "シングル サインオン: イベント 10589 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0fe962bb-e9bb-4107-a5fb-21c180d54e21
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56bb848711a627ceaea70085d770db7b0c759e9a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10589"></a><span data-ttu-id="c0de0-102">シングル サインオン: イベント 10589</span><span class="sxs-lookup"><span data-stu-id="c0de0-102">Single Sign-On: Event 10589</span></span>
## <a name="details"></a><span data-ttu-id="c0de0-103">詳細</span><span class="sxs-lookup"><span data-stu-id="c0de0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c0de0-104">製品名</span><span class="sxs-lookup"><span data-stu-id="c0de0-104">Product Name</span></span>|<span data-ttu-id="c0de0-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="c0de0-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="c0de0-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c0de0-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="c0de0-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c0de0-107">Event ID</span></span>|<span data-ttu-id="c0de0-108">10589</span><span class="sxs-lookup"><span data-stu-id="c0de0-108">10589</span></span>|  
|<span data-ttu-id="c0de0-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c0de0-109">Event Source</span></span>|<span data-ttu-id="c0de0-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c0de0-110">ENTSSO</span></span>|  
|<span data-ttu-id="c0de0-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c0de0-111">Component</span></span>|<span data-ttu-id="c0de0-112">なし</span><span class="sxs-lookup"><span data-stu-id="c0de0-112">N/A</span></span>|  
|<span data-ttu-id="c0de0-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c0de0-113">Symbolic Name</span></span>|<span data-ttu-id="c0de0-114">SSO_ERROR_BACKUP_SECRET_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="c0de0-114">SSO_ERROR_BACKUP_SECRET_REQUIRED</span></span>|  
|<span data-ttu-id="c0de0-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c0de0-115">Message Text</span></span>|<span data-ttu-id="c0de0-116">マスター シークレットがバックアップされていません。</span><span class="sxs-lookup"><span data-stu-id="c0de0-116">The master secret has not been backed up.</span></span> <span data-ttu-id="c0de0-117">マスター シークレットが失われると、SSO システムに保存されたすべての情報が完全に失われます。また、システムが正しく動作しなくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="c0de0-117">If you lose the master secret all the information stored in the SSO system will be lost permanently and your systems may fail to work correctly.</span></span> <span data-ttu-id="c0de0-118">SSO 管理ツールを使用して、マスター シークレットをバックアップしてください。</span><span class="sxs-lookup"><span data-stu-id="c0de0-118">Please use the SSO administration tools to back up your master secret.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c0de0-119">説明</span><span class="sxs-lookup"><span data-stu-id="c0de0-119">Explanation</span></span>  
 <span data-ttu-id="c0de0-120">マスター シークレットがバックアップされていません。</span><span class="sxs-lookup"><span data-stu-id="c0de0-120">The master secret has not been backed up.</span></span> <span data-ttu-id="c0de0-121">マスター シークレットが失われると、SSO システムに保存されたすべての情報が完全に失われます。また、システムが正しく動作しなくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="c0de0-121">If you lose the master secret all the information stored in the SSO system will be lost permanently and your systems may fail to work correctly.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c0de0-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c0de0-122">User Action</span></span>  
 <span data-ttu-id="c0de0-123">マスター シークレットのバックアップについては、次を参照してください。[マスタ シークレットの管理](../core/managing-the-master-secret.md)です。</span><span class="sxs-lookup"><span data-stu-id="c0de0-123">For information on backing up the master secret, see [Managing the Master Secret](../core/managing-the-master-secret.md).</span></span>
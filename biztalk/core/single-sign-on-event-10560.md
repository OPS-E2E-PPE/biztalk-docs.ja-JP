---
title: 'シングル サインオン: イベント 10560 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8677a807-2973-4753-8816-c93c45697d92
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d630dccdd21aaade843d4aa8fd7026d05fd71da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271386"
---
# <a name="single-sign-on-event-10560"></a><span data-ttu-id="4fe4c-102">シングル サインオン: イベント 10560</span><span class="sxs-lookup"><span data-stu-id="4fe4c-102">Single Sign-On: Event 10560</span></span>
## <a name="details"></a><span data-ttu-id="4fe4c-103">詳細</span><span class="sxs-lookup"><span data-stu-id="4fe4c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4fe4c-104">製品名</span><span class="sxs-lookup"><span data-stu-id="4fe4c-104">Product Name</span></span>|<span data-ttu-id="4fe4c-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="4fe4c-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="4fe4c-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="4fe4c-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="4fe4c-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4fe4c-107">Event ID</span></span>|<span data-ttu-id="4fe4c-108">10560</span><span class="sxs-lookup"><span data-stu-id="4fe4c-108">10560</span></span>|  
|<span data-ttu-id="4fe4c-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="4fe4c-109">Event Source</span></span>|<span data-ttu-id="4fe4c-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="4fe4c-110">ENTSSO</span></span>|  
|<span data-ttu-id="4fe4c-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="4fe4c-111">Component</span></span>|<span data-ttu-id="4fe4c-112">なし</span><span class="sxs-lookup"><span data-stu-id="4fe4c-112">N/A</span></span>|  
|<span data-ttu-id="4fe4c-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="4fe4c-113">Symbolic Name</span></span>|<span data-ttu-id="4fe4c-114">SSO_ERROR_BACKUP_SECRET_FAILED</span><span class="sxs-lookup"><span data-stu-id="4fe4c-114">SSO_ERROR_BACKUP_SECRET_FAILED</span></span>|  
|<span data-ttu-id="4fe4c-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="4fe4c-115">Message Text</span></span>|<span data-ttu-id="4fe4c-116">マスター シークレットをバックアップできませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="4fe4c-116">Failed to back up the master secrets.%r</span></span><br /><br /> <span data-ttu-id="4fe4c-117">ファイル名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="4fe4c-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="4fe4c-118">現在の MSID: %2 %r</span><span class="sxs-lookup"><span data-stu-id="4fe4c-118">Current MSID: %2%r</span></span><br /><br /> <span data-ttu-id="4fe4c-119">以前の MSID: %3 %r</span><span class="sxs-lookup"><span data-stu-id="4fe4c-119">Previous MSID: %3%r</span></span><br /><br /> <span data-ttu-id="4fe4c-120">クライアント ユーザー: %4 %r</span><span class="sxs-lookup"><span data-stu-id="4fe4c-120">Client User: %4%r</span></span><br /><br /> <span data-ttu-id="4fe4c-121">エラー コード: %5</span><span class="sxs-lookup"><span data-stu-id="4fe4c-121">Error Code: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4fe4c-122">説明</span><span class="sxs-lookup"><span data-stu-id="4fe4c-122">Explanation</span></span>  
 <span data-ttu-id="4fe4c-123">マスター シークレットをバックアップしようとしましたが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="4fe4c-123">An attempt to back up the master secret has failed.</span></span> <span data-ttu-id="4fe4c-124">このバックアップを実行しようとしたユーザーが使用したアクセス許可、パス、またはディレクトリが正しくない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4fe4c-124">The user attempting this backup may have had the wrong permissions, path, or directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4fe4c-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="4fe4c-125">User Action</span></span>  
 <span data-ttu-id="4fe4c-126">マスター シークレットのバックアップについては、次を参照してください。[マスタ シークレットの管理](../core/managing-the-master-secret.md)です。</span><span class="sxs-lookup"><span data-stu-id="4fe4c-126">For information on backing up the master secret, see [Managing the Master Secret](../core/managing-the-master-secret.md).</span></span>
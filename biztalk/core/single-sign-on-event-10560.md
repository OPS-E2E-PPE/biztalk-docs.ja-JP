---
title: 'シングル サインオン: イベント 10560 |Microsoft Docs'
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
ms.openlocfilehash: 82f9245b4eda9b6bf567aae1de2071d3e77aae04
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967755"
---
# <a name="single-sign-on-event-10560"></a><span data-ttu-id="f66f5-102">シングル サインオン: イベント 10560</span><span class="sxs-lookup"><span data-stu-id="f66f5-102">Single Sign-On: Event 10560</span></span>
## <a name="details"></a><span data-ttu-id="f66f5-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f66f5-103">Details</span></span>  
  
|                 |                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="f66f5-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f66f5-104">Product Name</span></span>   |                                                                                  <span data-ttu-id="f66f5-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="f66f5-105">Enterprise Single Sign-On</span></span>                                                                                  |
| <span data-ttu-id="f66f5-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f66f5-106">Product Version</span></span> |                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                  |
|    <span data-ttu-id="f66f5-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f66f5-107">Event ID</span></span>     |                                                                                            <span data-ttu-id="f66f5-108">10560</span><span class="sxs-lookup"><span data-stu-id="f66f5-108">10560</span></span>                                                                                            |
|  <span data-ttu-id="f66f5-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f66f5-109">Event Source</span></span>   |                                                                                           <span data-ttu-id="f66f5-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f66f5-110">ENTSSO</span></span>                                                                                            |
|    <span data-ttu-id="f66f5-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f66f5-111">Component</span></span>    |                                                                                             <span data-ttu-id="f66f5-112">なし</span><span class="sxs-lookup"><span data-stu-id="f66f5-112">N/A</span></span>                                                                                             |
|  <span data-ttu-id="f66f5-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f66f5-113">Symbolic Name</span></span>  |                                                                               <span data-ttu-id="f66f5-114">SSO_ERROR_BACKUP_SECRET_FAILED</span><span class="sxs-lookup"><span data-stu-id="f66f5-114">SSO_ERROR_BACKUP_SECRET_FAILED</span></span>                                                                                |
|  <span data-ttu-id="f66f5-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f66f5-115">Message Text</span></span>   | <span data-ttu-id="f66f5-116">マスター シークレットをバックアップできませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="f66f5-116">Failed to back up the master secrets.%r</span></span><br /><br /> <span data-ttu-id="f66f5-117">ファイル名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="f66f5-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="f66f5-118">現在の MSID: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="f66f5-118">Current MSID: %2%r</span></span><br /><br /> <span data-ttu-id="f66f5-119">以前の MSID: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="f66f5-119">Previous MSID: %3%r</span></span><br /><br /> <span data-ttu-id="f66f5-120">クライアント ユーザー: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="f66f5-120">Client User: %4%r</span></span><br /><br /> <span data-ttu-id="f66f5-121">エラー コード: %5</span><span class="sxs-lookup"><span data-stu-id="f66f5-121">Error Code: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="f66f5-122">説明</span><span class="sxs-lookup"><span data-stu-id="f66f5-122">Explanation</span></span>  
 <span data-ttu-id="f66f5-123">マスター シークレットをバックアップしようとしましたが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="f66f5-123">An attempt to back up the master secret has failed.</span></span> <span data-ttu-id="f66f5-124">このバックアップを実行しようとしたユーザーが使用したアクセス許可、パス、またはディレクトリが正しくない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f66f5-124">The user attempting this backup may have had the wrong permissions, path, or directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f66f5-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f66f5-125">User Action</span></span>  
 <span data-ttu-id="f66f5-126">マスター シークレットのバックアップについては、[マスター シークレットの管理](../core/managing-the-master-secret.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f66f5-126">For information on backing up the master secret, see [Managing the Master Secret](../core/managing-the-master-secret.md).</span></span>
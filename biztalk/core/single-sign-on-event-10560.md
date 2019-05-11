---
title: シングル サインオン:イベント 10560 |Microsoft Docs
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
ms.openlocfilehash: b43a9558cff9325cb7a5355213001d67a0218d43
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65296059"
---
# <a name="single-sign-on-event-10560"></a><span data-ttu-id="b2474-102">シングル サインオン:イベント 10560</span><span class="sxs-lookup"><span data-stu-id="b2474-102">Single Sign-On: Event 10560</span></span>
## <a name="details"></a><span data-ttu-id="b2474-103">詳細</span><span class="sxs-lookup"><span data-stu-id="b2474-103">Details</span></span>  
  
|                 |                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="b2474-104">製品名</span><span class="sxs-lookup"><span data-stu-id="b2474-104">Product Name</span></span>   |                                                                                  <span data-ttu-id="b2474-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="b2474-105">Enterprise Single Sign-On</span></span>                                                                                  |
| <span data-ttu-id="b2474-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="b2474-106">Product Version</span></span> |                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                  |
|    <span data-ttu-id="b2474-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="b2474-107">Event ID</span></span>     |                                                                                            <span data-ttu-id="b2474-108">10560</span><span class="sxs-lookup"><span data-stu-id="b2474-108">10560</span></span>                                                                                            |
|  <span data-ttu-id="b2474-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="b2474-109">Event Source</span></span>   |                                                                                           <span data-ttu-id="b2474-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="b2474-110">ENTSSO</span></span>                                                                                            |
|    <span data-ttu-id="b2474-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b2474-111">Component</span></span>    |                                                                                             <span data-ttu-id="b2474-112">なし</span><span class="sxs-lookup"><span data-stu-id="b2474-112">N/A</span></span>                                                                                             |
|  <span data-ttu-id="b2474-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="b2474-113">Symbolic Name</span></span>  |                                                                               <span data-ttu-id="b2474-114">SSO_ERROR_BACKUP_SECRET_FAILED</span><span class="sxs-lookup"><span data-stu-id="b2474-114">SSO_ERROR_BACKUP_SECRET_FAILED</span></span>                                                                                |
|  <span data-ttu-id="b2474-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="b2474-115">Message Text</span></span>   | <span data-ttu-id="b2474-116">マスター シークレットをバックアップできませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="b2474-116">Failed to back up the master secrets.%r</span></span><br /><br /> <span data-ttu-id="b2474-117">ファイル名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="b2474-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="b2474-118">現在の MSID: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="b2474-118">Current MSID: %2%r</span></span><br /><br /> <span data-ttu-id="b2474-119">以前の MSID: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="b2474-119">Previous MSID: %3%r</span></span><br /><br /> <span data-ttu-id="b2474-120">クライアント ユーザー: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="b2474-120">Client User: %4%r</span></span><br /><br /> <span data-ttu-id="b2474-121">エラー コード: %5</span><span class="sxs-lookup"><span data-stu-id="b2474-121">Error Code: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="b2474-122">説明</span><span class="sxs-lookup"><span data-stu-id="b2474-122">Explanation</span></span>  
 <span data-ttu-id="b2474-123">マスター シークレットをバックアップしようとしましたが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="b2474-123">An attempt to back up the master secret has failed.</span></span> <span data-ttu-id="b2474-124">このバックアップを実行しようとしたユーザーが使用したアクセス許可、パス、またはディレクトリが正しくない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b2474-124">The user attempting this backup may have had the wrong permissions, path, or directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b2474-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="b2474-125">User Action</span></span>  
 <span data-ttu-id="b2474-126">マスター シークレットのバックアップについては、次を参照してください。[マスター シークレットの管理](../core/managing-the-master-secret.md)します。</span><span class="sxs-lookup"><span data-stu-id="b2474-126">For information on backing up the master secret, see [Managing the Master Secret](../core/managing-the-master-secret.md).</span></span>
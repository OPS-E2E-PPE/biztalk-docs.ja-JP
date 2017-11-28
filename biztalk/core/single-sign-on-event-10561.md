---
title: "シングル サインオン: イベント 10561 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 770e6fc1-0854-4555-8f2a-5f199e3aaca7
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5148633c7fffabe0ef4bb4789fe4ded58336c10
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10561"></a><span data-ttu-id="5d192-102">シングル サインオン: イベント 10561</span><span class="sxs-lookup"><span data-stu-id="5d192-102">Single Sign-On: Event 10561</span></span>
## <a name="details"></a><span data-ttu-id="5d192-103">詳細</span><span class="sxs-lookup"><span data-stu-id="5d192-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5d192-104">製品名</span><span class="sxs-lookup"><span data-stu-id="5d192-104">Product Name</span></span>|<span data-ttu-id="5d192-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="5d192-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="5d192-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="5d192-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="5d192-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="5d192-107">Event ID</span></span>|<span data-ttu-id="5d192-108">10561</span><span class="sxs-lookup"><span data-stu-id="5d192-108">10561</span></span>|  
|<span data-ttu-id="5d192-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="5d192-109">Event Source</span></span>|<span data-ttu-id="5d192-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="5d192-110">ENTSSO</span></span>|  
|<span data-ttu-id="5d192-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5d192-111">Component</span></span>|<span data-ttu-id="5d192-112">なし</span><span class="sxs-lookup"><span data-stu-id="5d192-112">N/A</span></span>|  
|<span data-ttu-id="5d192-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="5d192-113">Symbolic Name</span></span>|<span data-ttu-id="5d192-114">SSO_ERROR_BACKUP_FAILED_MEDIA</span><span class="sxs-lookup"><span data-stu-id="5d192-114">SSO_ERROR_BACKUP_FAILED_MEDIA</span></span>|  
|<span data-ttu-id="5d192-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="5d192-115">Message Text</span></span>|<span data-ttu-id="5d192-116">マスター シークレットのバックアップのために指定するファイルは、NTFS ファイル システムまたはリムーバブル メディア上に存在している必要があります。%r</span><span class="sxs-lookup"><span data-stu-id="5d192-116">The file specified for backup of the master secrets must be on an NTFS file system or removable media.%r</span></span><br /><br /> <span data-ttu-id="5d192-117">ファイル名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="5d192-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="5d192-118">クライアント ユーザー: %2 %r</span><span class="sxs-lookup"><span data-stu-id="5d192-118">Client User: %2%r</span></span><br /><br /> <span data-ttu-id="5d192-119">クライアント コンピューターの場合: %3 %r</span><span class="sxs-lookup"><span data-stu-id="5d192-119">Client Computer: %3%r</span></span><br /><br /> <span data-ttu-id="5d192-120">エラー コード: %4</span><span class="sxs-lookup"><span data-stu-id="5d192-120">Error Code: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5d192-121">説明</span><span class="sxs-lookup"><span data-stu-id="5d192-121">Explanation</span></span>  
 <span data-ttu-id="5d192-122">FAT ファイルなどの無効なメディアを使用してバックアップしようとしました。</span><span class="sxs-lookup"><span data-stu-id="5d192-122">A backup was attempted using an invalid media, such as a FAT file.</span></span> <span data-ttu-id="5d192-123">マスター シークレットのバックアップのために指定するファイルは、NTFS ファイル システムまたはリムーバブル メディア上に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d192-123">The file specified for backup of the master secrets must be on an NTFS file system or removable media.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5d192-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="5d192-124">User Action</span></span>  
 <span data-ttu-id="5d192-125">メディアの形式を確認し、NTFS またはリムーバブル メディアであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5d192-125">Check the media format and make sure it is NTFS or removable.</span></span>
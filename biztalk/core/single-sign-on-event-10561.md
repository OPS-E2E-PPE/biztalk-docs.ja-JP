---
title: 'シングル サインオン: イベント 10561 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 770e6fc1-0854-4555-8f2a-5f199e3aaca7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 053b17fcb940383d58110378710aeb6bc8d3fbe6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992500"
---
# <a name="single-sign-on-event-10561"></a><span data-ttu-id="17802-102">シングル サインオン: イベント 10561</span><span class="sxs-lookup"><span data-stu-id="17802-102">Single Sign-On: Event 10561</span></span>
## <a name="details"></a><span data-ttu-id="17802-103">詳細</span><span class="sxs-lookup"><span data-stu-id="17802-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                 |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="17802-104">製品名</span><span class="sxs-lookup"><span data-stu-id="17802-104">Product Name</span></span>   |                                                                                                    <span data-ttu-id="17802-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="17802-105">Enterprise Single Sign-On</span></span>                                                                                                    |
| <span data-ttu-id="17802-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="17802-106">Product Version</span></span> |                                                                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                    |
|    <span data-ttu-id="17802-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="17802-107">Event ID</span></span>     |                                                                                                              <span data-ttu-id="17802-108">10561</span><span class="sxs-lookup"><span data-stu-id="17802-108">10561</span></span>                                                                                                              |
|  <span data-ttu-id="17802-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="17802-109">Event Source</span></span>   |                                                                                                             <span data-ttu-id="17802-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="17802-110">ENTSSO</span></span>                                                                                                              |
|    <span data-ttu-id="17802-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="17802-111">Component</span></span>    |                                                                                                               <span data-ttu-id="17802-112">なし</span><span class="sxs-lookup"><span data-stu-id="17802-112">N/A</span></span>                                                                                                               |
|  <span data-ttu-id="17802-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="17802-113">Symbolic Name</span></span>  |                                                                                                  <span data-ttu-id="17802-114">SSO_ERROR_BACKUP_FAILED_MEDIA</span><span class="sxs-lookup"><span data-stu-id="17802-114">SSO_ERROR_BACKUP_FAILED_MEDIA</span></span>                                                                                                  |
|  <span data-ttu-id="17802-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="17802-115">Message Text</span></span>   | <span data-ttu-id="17802-116">マスター シークレットのバックアップのために指定するファイルは、NTFS ファイル システムまたはリムーバブル メディア上に存在している必要があります。%r</span><span class="sxs-lookup"><span data-stu-id="17802-116">The file specified for backup of the master secrets must be on an NTFS file system or removable media.%r</span></span><br /><br /> <span data-ttu-id="17802-117">ファイル名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="17802-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="17802-118">クライアント ユーザー: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="17802-118">Client User: %2%r</span></span><br /><br /> <span data-ttu-id="17802-119">クライアント コンピューターの場合: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="17802-119">Client Computer: %3%r</span></span><br /><br /> <span data-ttu-id="17802-120">エラー コード: %4</span><span class="sxs-lookup"><span data-stu-id="17802-120">Error Code: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="17802-121">説明</span><span class="sxs-lookup"><span data-stu-id="17802-121">Explanation</span></span>  
 <span data-ttu-id="17802-122">FAT ファイルなどの無効なメディアを使用してバックアップしようとしました。</span><span class="sxs-lookup"><span data-stu-id="17802-122">A backup was attempted using an invalid media, such as a FAT file.</span></span> <span data-ttu-id="17802-123">マスター シークレットのバックアップのために指定するファイルは、NTFS ファイル システムまたはリムーバブル メディア上に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="17802-123">The file specified for backup of the master secrets must be on an NTFS file system or removable media.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="17802-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="17802-124">User Action</span></span>  
 <span data-ttu-id="17802-125">メディアの形式を確認し、NTFS またはリムーバブル メディアであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="17802-125">Check the media format and make sure it is NTFS or removable.</span></span>
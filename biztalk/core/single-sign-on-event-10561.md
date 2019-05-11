---
title: シングル サインオン:イベント 10561 |Microsoft Docs
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
ms.openlocfilehash: ce91071578747053c1966cd208a9251d3fbe835e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398845"
---
# <a name="single-sign-on-event-10561"></a><span data-ttu-id="be2df-102">シングル サインオン:イベント 10561</span><span class="sxs-lookup"><span data-stu-id="be2df-102">Single Sign-On: Event 10561</span></span>
## <a name="details"></a><span data-ttu-id="be2df-103">詳細</span><span class="sxs-lookup"><span data-stu-id="be2df-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                 |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="be2df-104">製品名</span><span class="sxs-lookup"><span data-stu-id="be2df-104">Product Name</span></span>   |                                                                                                    <span data-ttu-id="be2df-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="be2df-105">Enterprise Single Sign-On</span></span>                                                                                                    |
| <span data-ttu-id="be2df-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="be2df-106">Product Version</span></span> |                                                                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                    |
|    <span data-ttu-id="be2df-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="be2df-107">Event ID</span></span>     |                                                                                                              <span data-ttu-id="be2df-108">10561</span><span class="sxs-lookup"><span data-stu-id="be2df-108">10561</span></span>                                                                                                              |
|  <span data-ttu-id="be2df-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="be2df-109">Event Source</span></span>   |                                                                                                             <span data-ttu-id="be2df-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="be2df-110">ENTSSO</span></span>                                                                                                              |
|    <span data-ttu-id="be2df-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="be2df-111">Component</span></span>    |                                                                                                               <span data-ttu-id="be2df-112">なし</span><span class="sxs-lookup"><span data-stu-id="be2df-112">N/A</span></span>                                                                                                               |
|  <span data-ttu-id="be2df-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="be2df-113">Symbolic Name</span></span>  |                                                                                                  <span data-ttu-id="be2df-114">SSO_ERROR_BACKUP_FAILED_MEDIA</span><span class="sxs-lookup"><span data-stu-id="be2df-114">SSO_ERROR_BACKUP_FAILED_MEDIA</span></span>                                                                                                  |
|  <span data-ttu-id="be2df-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="be2df-115">Message Text</span></span>   | <span data-ttu-id="be2df-116">マスタ シークレットのバックアップの指定されたファイルは、NTFS ファイル システムまたはリムーバブル media.%r にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="be2df-116">The file specified for backup of the master secrets must be on an NTFS file system or removable media.%r</span></span><br /><br /> <span data-ttu-id="be2df-117">ファイル名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="be2df-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="be2df-118">クライアント ユーザー: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="be2df-118">Client User: %2%r</span></span><br /><br /> <span data-ttu-id="be2df-119">クライアント コンピューターの場合: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="be2df-119">Client Computer: %3%r</span></span><br /><br /> <span data-ttu-id="be2df-120">エラー コード: %4</span><span class="sxs-lookup"><span data-stu-id="be2df-120">Error Code: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="be2df-121">説明</span><span class="sxs-lookup"><span data-stu-id="be2df-121">Explanation</span></span>  
 <span data-ttu-id="be2df-122">バックアップは、FAT ファイルなどの無効なメディアを使用しようとしました。</span><span class="sxs-lookup"><span data-stu-id="be2df-122">A backup was attempted using an invalid media, such as a FAT file.</span></span> <span data-ttu-id="be2df-123">マスタ シークレットのバックアップの指定されたファイルは、NTFS ファイル システムまたはリムーバブル メディア上にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="be2df-123">The file specified for backup of the master secrets must be on an NTFS file system or removable media.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="be2df-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="be2df-124">User Action</span></span>  
 <span data-ttu-id="be2df-125">メディア形式を確認し、NTFS であることを確認またはリムーバブルします。</span><span class="sxs-lookup"><span data-stu-id="be2df-125">Check the media format and make sure it is NTFS or removable.</span></span>
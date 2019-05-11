---
title: シングル サインオン:イベント 10759 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5347f3d6-d31a-4c00-a64c-c0b0f680de88
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 966cc847d442e61353ea862e908b12d7d4b4f3d1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65307478"
---
# <a name="single-sign-on-event-10759"></a><span data-ttu-id="78808-102">シングル サインオン:イベント 10759</span><span class="sxs-lookup"><span data-stu-id="78808-102">Single Sign-On: Event 10759</span></span>
## <a name="details"></a><span data-ttu-id="78808-103">詳細</span><span class="sxs-lookup"><span data-stu-id="78808-103">Details</span></span>  
  
|                 |                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="78808-104">製品名</span><span class="sxs-lookup"><span data-stu-id="78808-104">Product Name</span></span>   |                                             <span data-ttu-id="78808-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="78808-105">Enterprise Single Sign-On</span></span>                                             |
| <span data-ttu-id="78808-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="78808-106">Product Version</span></span> |                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                             |
|    <span data-ttu-id="78808-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="78808-107">Event ID</span></span>     |                                                       <span data-ttu-id="78808-108">10759</span><span class="sxs-lookup"><span data-stu-id="78808-108">10759</span></span>                                                       |
|  <span data-ttu-id="78808-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="78808-109">Event Source</span></span>   |                                                      <span data-ttu-id="78808-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="78808-110">ENTSSO</span></span>                                                       |
|    <span data-ttu-id="78808-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="78808-111">Component</span></span>    |                                                        <span data-ttu-id="78808-112">なし</span><span class="sxs-lookup"><span data-stu-id="78808-112">N/A</span></span>                                                        |
|  <span data-ttu-id="78808-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="78808-113">Symbolic Name</span></span>  |                                       <span data-ttu-id="78808-114">ENTSSO_E_BACKUP_RESTORE_FAILED_MEDIA</span><span class="sxs-lookup"><span data-stu-id="78808-114">ENTSSO_E_BACKUP_RESTORE_FAILED_MEDIA</span></span>                                        |
|  <span data-ttu-id="78808-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="78808-115">Message Text</span></span>   | <span data-ttu-id="78808-116">マスター シークレットのバックアップまたは復元に指定されたファイルは、NTFS ファイル システムまたはリムーバブル メディアでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="78808-116">The file specified for backup or restore of the master secrets must be on an NTFS file system or removable media.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="78808-117">説明</span><span class="sxs-lookup"><span data-stu-id="78808-117">Explanation</span></span>  
 <span data-ttu-id="78808-118">NTFS ファイル システムまたはリムーバブル メディアのみを保護することができます。</span><span class="sxs-lookup"><span data-stu-id="78808-118">Only NTFS file systems or removable media can be secured.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="78808-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="78808-119">User Action</span></span>  
 <span data-ttu-id="78808-120">マスター シークレットをバックアップするリムーバブル メディアの NTFS ファイル システムをいずれかに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="78808-120">Switch to either an NTFS file system of removable media to back up the master secret.</span></span>
---
title: 'シングル サインオン: イベント 10759 |Microsoft ドキュメント'
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
ms.openlocfilehash: 81ff42b71499df5848a55848b3dc1067adb830bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277202"
---
# <a name="single-sign-on-event-10759"></a><span data-ttu-id="a71de-102">シングル サインオン: イベント 10759</span><span class="sxs-lookup"><span data-stu-id="a71de-102">Single Sign-On: Event 10759</span></span>
## <a name="details"></a><span data-ttu-id="a71de-103">詳細</span><span class="sxs-lookup"><span data-stu-id="a71de-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a71de-104">製品名</span><span class="sxs-lookup"><span data-stu-id="a71de-104">Product Name</span></span>|<span data-ttu-id="a71de-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="a71de-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="a71de-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="a71de-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="a71de-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="a71de-107">Event ID</span></span>|<span data-ttu-id="a71de-108">10759</span><span class="sxs-lookup"><span data-stu-id="a71de-108">10759</span></span>|  
|<span data-ttu-id="a71de-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="a71de-109">Event Source</span></span>|<span data-ttu-id="a71de-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a71de-110">ENTSSO</span></span>|  
|<span data-ttu-id="a71de-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a71de-111">Component</span></span>|<span data-ttu-id="a71de-112">なし</span><span class="sxs-lookup"><span data-stu-id="a71de-112">N/A</span></span>|  
|<span data-ttu-id="a71de-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="a71de-113">Symbolic Name</span></span>|<span data-ttu-id="a71de-114">ENTSSO_E_BACKUP_RESTORE_FAILED_MEDIA</span><span class="sxs-lookup"><span data-stu-id="a71de-114">ENTSSO_E_BACKUP_RESTORE_FAILED_MEDIA</span></span>|  
|<span data-ttu-id="a71de-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="a71de-115">Message Text</span></span>|<span data-ttu-id="a71de-116">マスター シークレットのバックアップまたは復元のために指定するファイルは、NTFS ファイル システムまたはリムーバブル メディア上に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="a71de-116">The file specified for backup or restore of the master secrets must be on an NTFS file system or removable media.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a71de-117">説明</span><span class="sxs-lookup"><span data-stu-id="a71de-117">Explanation</span></span>  
 <span data-ttu-id="a71de-118">セキュリティで保護できるのは、NTFS ファイル システムまたはリムーバブル メディアのみです。</span><span class="sxs-lookup"><span data-stu-id="a71de-118">Only NTFS file systems or removable media can be secured.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a71de-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="a71de-119">User Action</span></span>  
 <span data-ttu-id="a71de-120">NTFS ファイル システムまたはリムーバブル メディアに切り替えて、マスター シークレットをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="a71de-120">Switch to either an NTFS file system of removable media to back up the master secret.</span></span>
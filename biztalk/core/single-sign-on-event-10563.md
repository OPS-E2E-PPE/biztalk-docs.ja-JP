---
title: "シングル サインオン: イベント 10563 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7c944cc4-7fe0-41cc-9608-ee954e8222e0
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2ff30e245350004d798b0c6c2950b5bab345e77
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10563"></a><span data-ttu-id="31cc0-102">シングル サインオン: イベント 10563</span><span class="sxs-lookup"><span data-stu-id="31cc0-102">Single Sign-On: Event 10563</span></span>
## <a name="details"></a><span data-ttu-id="31cc0-103">詳細</span><span class="sxs-lookup"><span data-stu-id="31cc0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="31cc0-104">製品名</span><span class="sxs-lookup"><span data-stu-id="31cc0-104">Product Name</span></span>|<span data-ttu-id="31cc0-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="31cc0-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="31cc0-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="31cc0-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="31cc0-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="31cc0-107">Event ID</span></span>|<span data-ttu-id="31cc0-108">10563</span><span class="sxs-lookup"><span data-stu-id="31cc0-108">10563</span></span>|  
|<span data-ttu-id="31cc0-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="31cc0-109">Event Source</span></span>|<span data-ttu-id="31cc0-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="31cc0-110">ENTSSO</span></span>|  
|<span data-ttu-id="31cc0-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="31cc0-111">Component</span></span>|<span data-ttu-id="31cc0-112">なし</span><span class="sxs-lookup"><span data-stu-id="31cc0-112">N/A</span></span>|  
|<span data-ttu-id="31cc0-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="31cc0-113">Symbolic Name</span></span>|<span data-ttu-id="31cc0-114">SSO_WARN_PERFMON_FAILED</span><span class="sxs-lookup"><span data-stu-id="31cc0-114">SSO_WARN_PERFMON_FAILED</span></span>|  
|<span data-ttu-id="31cc0-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="31cc0-115">Message Text</span></span>|<span data-ttu-id="31cc0-116">パフォーマンス監視を開始できませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="31cc0-116">Performance monitoring failed to start.%r</span></span><br /><br /> <span data-ttu-id="31cc0-117">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="31cc0-117">Error Code: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="31cc0-118">説明</span><span class="sxs-lookup"><span data-stu-id="31cc0-118">Explanation</span></span>  
 <span data-ttu-id="31cc0-119">パフォーマンス監視を開始できませんでした。</span><span class="sxs-lookup"><span data-stu-id="31cc0-119">Performance monitoring failed to start.</span></span> <span data-ttu-id="31cc0-120">システムは通常の実行を続行できますが、パフォーマンス監視は使用できません。</span><span class="sxs-lookup"><span data-stu-id="31cc0-120">The system will continue to run normally but performance monitoring will not be available.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="31cc0-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="31cc0-121">User Action</span></span>  
 <span data-ttu-id="31cc0-122">perfmon ユーティリティのアンインストールと再インストールが必要である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="31cc0-122">It may be necessary to uninstall and reinstall the perfmon utility.</span></span>
---
title: 'シングル サインオン: イベント 11026 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e39b252d-2ed0-4006-aac2-4dce6504afb2
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ecee6d3c3e6dcf01b8489c4041f4aab717eba585
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278282"
---
# <a name="single-sign-on-event-11026"></a><span data-ttu-id="393a2-102">シングル サインオン: イベント 11026</span><span class="sxs-lookup"><span data-stu-id="393a2-102">Single Sign-On: Event 11026</span></span>
## <a name="details"></a><span data-ttu-id="393a2-103">詳細</span><span class="sxs-lookup"><span data-stu-id="393a2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="393a2-104">製品名</span><span class="sxs-lookup"><span data-stu-id="393a2-104">Product Name</span></span>|<span data-ttu-id="393a2-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="393a2-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="393a2-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="393a2-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="393a2-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="393a2-107">Event ID</span></span>|<span data-ttu-id="393a2-108">11026</span><span class="sxs-lookup"><span data-stu-id="393a2-108">11026</span></span>|  
|<span data-ttu-id="393a2-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="393a2-109">Event Source</span></span>|<span data-ttu-id="393a2-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="393a2-110">ENTSSO</span></span>|  
|<span data-ttu-id="393a2-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="393a2-111">Component</span></span>|<span data-ttu-id="393a2-112">なし</span><span class="sxs-lookup"><span data-stu-id="393a2-112">N/A</span></span>|  
|<span data-ttu-id="393a2-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="393a2-113">Symbolic Name</span></span>|<span data-ttu-id="393a2-114">SSO_WARN_EXISTING_GROUP_MAPPING</span><span class="sxs-lookup"><span data-stu-id="393a2-114">SSO_WARN_EXISTING_GROUP_MAPPING</span></span>|  
|<span data-ttu-id="393a2-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="393a2-115">Message Text</span></span>|<span data-ttu-id="393a2-116">既存のマッピングとの競合があるため、新しいグループ マッピングを作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="393a2-116">A new group mapping could not be created because there is a conflict with an existing mapping.</span></span> <span data-ttu-id="393a2-117">既存のマッピングを削除してから、再度実行してください。%r</span><span class="sxs-lookup"><span data-stu-id="393a2-117">Please delete the existing mapping and try again.%r</span></span><br /><br /> <span data-ttu-id="393a2-118">既存のマッピング: %1 %r</span><span class="sxs-lookup"><span data-stu-id="393a2-118">Existing Mapping: %1%r</span></span><br /><br /> <span data-ttu-id="393a2-119">新しいマッピング: %2 %r</span><span class="sxs-lookup"><span data-stu-id="393a2-119">New Mapping: %2%r</span></span><br /><br /> <span data-ttu-id="393a2-120">外部アカウント: %3 %r</span><span class="sxs-lookup"><span data-stu-id="393a2-120">External Account: %3%r</span></span><br /><br /> <span data-ttu-id="393a2-121">アプリケーション名: %4</span><span class="sxs-lookup"><span data-stu-id="393a2-121">Application Name: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="393a2-122">説明</span><span class="sxs-lookup"><span data-stu-id="393a2-122">Explanation</span></span>  
 <span data-ttu-id="393a2-123">最も可能性が高い原因は、システムが古いバージョンのエンタープライズ シングル サインオンと古いグループ アプリケーションを使用していることです。</span><span class="sxs-lookup"><span data-stu-id="393a2-123">The most likely cause is that your system is using an old version of Enterprise Single Sign-On, and old group applications.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="393a2-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="393a2-124">User Action</span></span>  
 <span data-ttu-id="393a2-125">警告で指摘されているように、マッピングを削除して作成しなおします。</span><span class="sxs-lookup"><span data-stu-id="393a2-125">Delete and recreate the mapping as suggested in the warning.</span></span> <span data-ttu-id="393a2-126">これが失敗する場合は、より新しいバージョンのエンタープライズ シングル サインオンにアップグレードすることが必要な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="393a2-126">If this fails, you may need to upgrade to a more recent version of Enterprise Single Sign-On.</span></span>
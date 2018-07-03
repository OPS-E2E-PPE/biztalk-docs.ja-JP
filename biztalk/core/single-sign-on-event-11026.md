---
title: 'シングル サインオン: イベント 11026 |Microsoft Docs'
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
ms.openlocfilehash: 452ccc24174a1e32a133c0ccc6c7a0b5f09c530f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013491"
---
# <a name="single-sign-on-event-11026"></a><span data-ttu-id="40f7e-102">シングル サインオン: イベント 11026</span><span class="sxs-lookup"><span data-stu-id="40f7e-102">Single Sign-On: Event 11026</span></span>
## <a name="details"></a><span data-ttu-id="40f7e-103">詳細</span><span class="sxs-lookup"><span data-stu-id="40f7e-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="40f7e-104">製品名</span><span class="sxs-lookup"><span data-stu-id="40f7e-104">Product Name</span></span>   |                                                                                                                                <span data-ttu-id="40f7e-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="40f7e-105">Enterprise Single Sign-On</span></span>                                                                                                                                |
| <span data-ttu-id="40f7e-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="40f7e-106">Product Version</span></span> |                                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                |
|    <span data-ttu-id="40f7e-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="40f7e-107">Event ID</span></span>     |                                                                                                                                          <span data-ttu-id="40f7e-108">11026</span><span class="sxs-lookup"><span data-stu-id="40f7e-108">11026</span></span>                                                                                                                                          |
|  <span data-ttu-id="40f7e-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="40f7e-109">Event Source</span></span>   |                                                                                                                                         <span data-ttu-id="40f7e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="40f7e-110">ENTSSO</span></span>                                                                                                                                          |
|    <span data-ttu-id="40f7e-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="40f7e-111">Component</span></span>    |                                                                                                                                           <span data-ttu-id="40f7e-112">なし</span><span class="sxs-lookup"><span data-stu-id="40f7e-112">N/A</span></span>                                                                                                                                           |
|  <span data-ttu-id="40f7e-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="40f7e-113">Symbolic Name</span></span>  |                                                                                                                             <span data-ttu-id="40f7e-114">SSO_WARN_EXISTING_GROUP_MAPPING</span><span class="sxs-lookup"><span data-stu-id="40f7e-114">SSO_WARN_EXISTING_GROUP_MAPPING</span></span>                                                                                                                             |
|  <span data-ttu-id="40f7e-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="40f7e-115">Message Text</span></span>   | <span data-ttu-id="40f7e-116">既存のマッピングとの競合があるため、新しいグループ マッピングを作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="40f7e-116">A new group mapping could not be created because there is a conflict with an existing mapping.</span></span> <span data-ttu-id="40f7e-117">既存のマッピングを削除してから、再度実行してください。%r</span><span class="sxs-lookup"><span data-stu-id="40f7e-117">Please delete the existing mapping and try again.%r</span></span><br /><br /> <span data-ttu-id="40f7e-118">既存のマッピング: % 1 %r</span><span class="sxs-lookup"><span data-stu-id="40f7e-118">Existing Mapping: %1%r</span></span><br /><br /> <span data-ttu-id="40f7e-119">新しいマッピング: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="40f7e-119">New Mapping: %2%r</span></span><br /><br /> <span data-ttu-id="40f7e-120">外部アカウント: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="40f7e-120">External Account: %3%r</span></span><br /><br /> <span data-ttu-id="40f7e-121">アプリケーション名: %4</span><span class="sxs-lookup"><span data-stu-id="40f7e-121">Application Name: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="40f7e-122">説明</span><span class="sxs-lookup"><span data-stu-id="40f7e-122">Explanation</span></span>  
 <span data-ttu-id="40f7e-123">最も可能性が高い原因は、システムが古いバージョンのエンタープライズ シングル サインオンと古いグループ アプリケーションを使用していることです。</span><span class="sxs-lookup"><span data-stu-id="40f7e-123">The most likely cause is that your system is using an old version of Enterprise Single Sign-On, and old group applications.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="40f7e-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="40f7e-124">User Action</span></span>  
 <span data-ttu-id="40f7e-125">警告で指摘されているように、マッピングを削除して作成しなおします。</span><span class="sxs-lookup"><span data-stu-id="40f7e-125">Delete and recreate the mapping as suggested in the warning.</span></span> <span data-ttu-id="40f7e-126">これが失敗する場合は、より新しいバージョンのエンタープライズ シングル サインオンにアップグレードすることが必要な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="40f7e-126">If this fails, you may need to upgrade to a more recent version of Enterprise Single Sign-On.</span></span>
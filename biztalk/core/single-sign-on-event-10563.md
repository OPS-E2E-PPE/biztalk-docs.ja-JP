---
title: シングル サインオン:イベント 10563 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c944cc4-7fe0-41cc-9608-ee954e8222e0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b735a435a076b873b8462f3b794012f731956ad1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398807"
---
# <a name="single-sign-on-event-10563"></a><span data-ttu-id="0694e-102">シングル サインオン:イベント 10563</span><span class="sxs-lookup"><span data-stu-id="0694e-102">Single Sign-On: Event 10563</span></span>
## <a name="details"></a><span data-ttu-id="0694e-103">詳細</span><span class="sxs-lookup"><span data-stu-id="0694e-103">Details</span></span>  
  
|                 |                                                                      |
|-----------------|----------------------------------------------------------------------|
|  <span data-ttu-id="0694e-104">製品名</span><span class="sxs-lookup"><span data-stu-id="0694e-104">Product Name</span></span>   |                      <span data-ttu-id="0694e-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="0694e-105">Enterprise Single Sign-On</span></span>                       |
| <span data-ttu-id="0694e-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="0694e-106">Product Version</span></span> |      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]      |
|    <span data-ttu-id="0694e-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0694e-107">Event ID</span></span>     |                                <span data-ttu-id="0694e-108">10563</span><span class="sxs-lookup"><span data-stu-id="0694e-108">10563</span></span>                                 |
|  <span data-ttu-id="0694e-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="0694e-109">Event Source</span></span>   |                                <span data-ttu-id="0694e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0694e-110">ENTSSO</span></span>                                |
|    <span data-ttu-id="0694e-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0694e-111">Component</span></span>    |                                 <span data-ttu-id="0694e-112">なし</span><span class="sxs-lookup"><span data-stu-id="0694e-112">N/A</span></span>                                  |
|  <span data-ttu-id="0694e-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="0694e-113">Symbolic Name</span></span>  |                       <span data-ttu-id="0694e-114">SSO_WARN_PERFMON_FAILED</span><span class="sxs-lookup"><span data-stu-id="0694e-114">SSO_WARN_PERFMON_FAILED</span></span>                        |
|  <span data-ttu-id="0694e-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="0694e-115">Message Text</span></span>   | <span data-ttu-id="0694e-116">パフォーマンスの監視を start.%r できませんでした。</span><span class="sxs-lookup"><span data-stu-id="0694e-116">Performance monitoring failed to start.%r</span></span><br /><br /> <span data-ttu-id="0694e-117">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="0694e-117">Error Code: %1</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="0694e-118">説明</span><span class="sxs-lookup"><span data-stu-id="0694e-118">Explanation</span></span>  
 <span data-ttu-id="0694e-119">パフォーマンスの監視を開始できませんでした。</span><span class="sxs-lookup"><span data-stu-id="0694e-119">Performance monitoring failed to start.</span></span> <span data-ttu-id="0694e-120">システムは引き続き通常どおりに実行がパフォーマンスの監視は使用できません。</span><span class="sxs-lookup"><span data-stu-id="0694e-120">The system will continue to run normally but performance monitoring will not be available.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0694e-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="0694e-121">User Action</span></span>  
 <span data-ttu-id="0694e-122">アンインストールして、perfmon ユーティリティを再インストールする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="0694e-122">It may be necessary to uninstall and reinstall the perfmon utility.</span></span>
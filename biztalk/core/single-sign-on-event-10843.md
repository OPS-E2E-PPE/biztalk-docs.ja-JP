---
title: "シングル サインオン: イベント 10843 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 847e464e-5733-4703-905f-d44a4c4f5cc3
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd86a39d515858e1cda09317ba6139bc67c95ed4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10843"></a><span data-ttu-id="bfc0b-102">シングル サインオン: イベント 10843</span><span class="sxs-lookup"><span data-stu-id="bfc0b-102">Single Sign-On: Event 10843</span></span>
## <a name="details"></a><span data-ttu-id="bfc0b-103">詳細</span><span class="sxs-lookup"><span data-stu-id="bfc0b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bfc0b-104">製品名</span><span class="sxs-lookup"><span data-stu-id="bfc0b-104">Product Name</span></span>|<span data-ttu-id="bfc0b-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="bfc0b-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="bfc0b-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="bfc0b-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="bfc0b-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="bfc0b-107">Event ID</span></span>|<span data-ttu-id="bfc0b-108">10843</span><span class="sxs-lookup"><span data-stu-id="bfc0b-108">10843</span></span>|  
|<span data-ttu-id="bfc0b-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="bfc0b-109">Event Source</span></span>|<span data-ttu-id="bfc0b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="bfc0b-110">ENTSSO</span></span>|  
|<span data-ttu-id="bfc0b-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bfc0b-111">Component</span></span>|<span data-ttu-id="bfc0b-112">なし</span><span class="sxs-lookup"><span data-stu-id="bfc0b-112">N/A</span></span>|  
|<span data-ttu-id="bfc0b-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="bfc0b-113">Symbolic Name</span></span>|<span data-ttu-id="bfc0b-114">ENTSSO_E_NO_SECRET2</span><span class="sxs-lookup"><span data-stu-id="bfc0b-114">ENTSSO_E_NO_SECRET2</span></span>|  
|<span data-ttu-id="bfc0b-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="bfc0b-115">Message Text</span></span>|<span data-ttu-id="bfc0b-116">マスター シークレット サーバーからシークレットを入手できないため、暗号化または解読を実行できません。</span><span class="sxs-lookup"><span data-stu-id="bfc0b-116">Cannot perform encryption or decryption because the secret is not available from the master secret server.</span></span> <span data-ttu-id="bfc0b-117">イベント ログ (コンピューター '%1' 上) で関連エラーを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfc0b-117">See the event log (on computer ‘%1’) for related errors.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bfc0b-118">説明</span><span class="sxs-lookup"><span data-stu-id="bfc0b-118">Explanation</span></span>  
 <span data-ttu-id="bfc0b-119">アクセスが拒否されました。</span><span class="sxs-lookup"><span data-stu-id="bfc0b-119">Access is denied.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bfc0b-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="bfc0b-120">User Action</span></span>  
 <span data-ttu-id="bfc0b-121">マスター シークレット サーバーがオフライン、または、マスター シークレット サーバーに必要なマスター シークレットがありません。</span><span class="sxs-lookup"><span data-stu-id="bfc0b-121">Either the master secret server is off-line, or the master secret server is missing the required master secret.</span></span> <span data-ttu-id="bfc0b-122">指定されたコンピューター上のイベント ログで関連エラーを参照します。</span><span class="sxs-lookup"><span data-stu-id="bfc0b-122">See the event log on the specified computer for related errors.</span></span>
---
title: "シングル サインオン: イベント 11049 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 031ec1a6-4b2b-46b2-9dbb-5525d758651f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45ac6095950e02e7e73ab287b180bc22d88b4191
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11049"></a><span data-ttu-id="41962-102">シングル サインオン: イベント 11049</span><span class="sxs-lookup"><span data-stu-id="41962-102">Single Sign-On: Event 11049</span></span>
## <a name="details"></a><span data-ttu-id="41962-103">詳細</span><span class="sxs-lookup"><span data-stu-id="41962-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="41962-104">製品名</span><span class="sxs-lookup"><span data-stu-id="41962-104">Product Name</span></span>|<span data-ttu-id="41962-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="41962-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="41962-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="41962-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="41962-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="41962-107">Event ID</span></span>|<span data-ttu-id="41962-108">11049</span><span class="sxs-lookup"><span data-stu-id="41962-108">11049</span></span>|  
|<span data-ttu-id="41962-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="41962-109">Event Source</span></span>|<span data-ttu-id="41962-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="41962-110">ENTSSO</span></span>|  
|<span data-ttu-id="41962-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="41962-111">Component</span></span>|<span data-ttu-id="41962-112">なし</span><span class="sxs-lookup"><span data-stu-id="41962-112">N/A</span></span>|  
|<span data-ttu-id="41962-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="41962-113">Symbolic Name</span></span>|<span data-ttu-id="41962-114">SSO_ERROR_DTC_FAILED</span><span class="sxs-lookup"><span data-stu-id="41962-114">SSO_ERROR_DTC_FAILED</span></span>|  
|<span data-ttu-id="41962-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="41962-115">Message Text</span></span>|<span data-ttu-id="41962-116">MSDTC を取得できませんでした。</span><span class="sxs-lookup"><span data-stu-id="41962-116">Could not get MSDTC.</span></span> <span data-ttu-id="41962-117">SSO を正しく機能させるには MSDTC が必要です。</span><span class="sxs-lookup"><span data-stu-id="41962-117">SSO requires MSDTC for correct operation.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="41962-118">説明</span><span class="sxs-lookup"><span data-stu-id="41962-118">Explanation</span></span>  
 <span data-ttu-id="41962-119">ENTSSO システムが、Microsoft 分散トランザクション コーディネーター (MSDTC) に接続できませんでした。</span><span class="sxs-lookup"><span data-stu-id="41962-119">The ENTSSO system could not connect to the Microsoft Distributed Transaction Coordinator (MSDTC).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="41962-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="41962-120">User Action</span></span>  
 <span data-ttu-id="41962-121">MSDTC が現在動作しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="41962-121">Check to see if MSDTC is currently operational.</span></span>  
  
 <span data-ttu-id="41962-122">MSDTC の問題に関するヘルプを参照するには、次を参照してください。 [MSDTC の問題のトラブルシューティング](../core/troubleshooting-problems-with-msdtc.md)です。</span><span class="sxs-lookup"><span data-stu-id="41962-122">For help on MSDTC issues, see [Troubleshooting Problems with MSDTC](../core/troubleshooting-problems-with-msdtc.md).</span></span>
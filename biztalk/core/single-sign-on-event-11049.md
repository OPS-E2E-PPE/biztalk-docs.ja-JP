---
title: 'シングル サインオン: イベント 11049 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 031ec1a6-4b2b-46b2-9dbb-5525d758651f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b86cf3d5361a912cd976d8a27e83981b71237e2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997507"
---
# <a name="single-sign-on-event-11049"></a><span data-ttu-id="7dd6b-102">シングル サインオン: イベント 11049</span><span class="sxs-lookup"><span data-stu-id="7dd6b-102">Single Sign-On: Event 11049</span></span>
## <a name="details"></a><span data-ttu-id="7dd6b-103">詳細</span><span class="sxs-lookup"><span data-stu-id="7dd6b-103">Details</span></span>  
  
|                 |                                                                |
|-----------------|----------------------------------------------------------------|
|  <span data-ttu-id="7dd6b-104">製品名</span><span class="sxs-lookup"><span data-stu-id="7dd6b-104">Product Name</span></span>   |                   <span data-ttu-id="7dd6b-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="7dd6b-105">Enterprise Single Sign-On</span></span>                    |
| <span data-ttu-id="7dd6b-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="7dd6b-106">Product Version</span></span> |   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]   |
|    <span data-ttu-id="7dd6b-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7dd6b-107">Event ID</span></span>     |                             <span data-ttu-id="7dd6b-108">11049</span><span class="sxs-lookup"><span data-stu-id="7dd6b-108">11049</span></span>                              |
|  <span data-ttu-id="7dd6b-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="7dd6b-109">Event Source</span></span>   |                             <span data-ttu-id="7dd6b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="7dd6b-110">ENTSSO</span></span>                             |
|    <span data-ttu-id="7dd6b-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7dd6b-111">Component</span></span>    |                              <span data-ttu-id="7dd6b-112">なし</span><span class="sxs-lookup"><span data-stu-id="7dd6b-112">N/A</span></span>                               |
|  <span data-ttu-id="7dd6b-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="7dd6b-113">Symbolic Name</span></span>  |                      <span data-ttu-id="7dd6b-114">SSO_ERROR_DTC_FAILED</span><span class="sxs-lookup"><span data-stu-id="7dd6b-114">SSO_ERROR_DTC_FAILED</span></span>                      |
|  <span data-ttu-id="7dd6b-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="7dd6b-115">Message Text</span></span>   | <span data-ttu-id="7dd6b-116">MSDTC を取得できませんでした。</span><span class="sxs-lookup"><span data-stu-id="7dd6b-116">Could not get MSDTC.</span></span> <span data-ttu-id="7dd6b-117">SSO を正しく機能させるには MSDTC が必要です。</span><span class="sxs-lookup"><span data-stu-id="7dd6b-117">SSO requires MSDTC for correct operation.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="7dd6b-118">説明</span><span class="sxs-lookup"><span data-stu-id="7dd6b-118">Explanation</span></span>  
 <span data-ttu-id="7dd6b-119">ENTSSO システムが、Microsoft 分散トランザクション コーディネーター (MSDTC) に接続できませんでした。</span><span class="sxs-lookup"><span data-stu-id="7dd6b-119">The ENTSSO system could not connect to the Microsoft Distributed Transaction Coordinator (MSDTC).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7dd6b-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="7dd6b-120">User Action</span></span>  
 <span data-ttu-id="7dd6b-121">MSDTC が現在動作しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="7dd6b-121">Check to see if MSDTC is currently operational.</span></span>  
  
 <span data-ttu-id="7dd6b-122">MSDTC の問題に関するヘルプは、次を参照してください。 [MSDTC を使用した問題のトラブルシューティング](../core/troubleshooting-problems-with-msdtc.md)します。</span><span class="sxs-lookup"><span data-stu-id="7dd6b-122">For help on MSDTC issues, see [Troubleshooting Problems with MSDTC](../core/troubleshooting-problems-with-msdtc.md).</span></span>
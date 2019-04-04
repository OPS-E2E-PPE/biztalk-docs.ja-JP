---
title: 'シングル サインオン: イベント 10788 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: deeb8859-6b2e-452d-a7e5-0cb10de68bd2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1bf8d17abd7fd5652821b998cae34915e7777f2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019666"
---
# <a name="single-sign-on-event-10788"></a><span data-ttu-id="64a73-102">シングル サインオン: イベント 10788</span><span class="sxs-lookup"><span data-stu-id="64a73-102">Single Sign-On: Event 10788</span></span>
## <a name="details"></a><span data-ttu-id="64a73-103">詳細</span><span class="sxs-lookup"><span data-stu-id="64a73-103">Details</span></span>  
  
|                 |                                                                                                                                          |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="64a73-104">製品名</span><span class="sxs-lookup"><span data-stu-id="64a73-104">Product Name</span></span>   |                                                        <span data-ttu-id="64a73-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="64a73-105">Enterprise Single Sign-On</span></span>                                                         |
| <span data-ttu-id="64a73-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="64a73-106">Product Version</span></span> |                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                        |
|    <span data-ttu-id="64a73-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="64a73-107">Event ID</span></span>     |                                                                  <span data-ttu-id="64a73-108">10788</span><span class="sxs-lookup"><span data-stu-id="64a73-108">10788</span></span>                                                                   |
|  <span data-ttu-id="64a73-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="64a73-109">Event Source</span></span>   |                                                                  <span data-ttu-id="64a73-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="64a73-110">ENTSSO</span></span>                                                                  |
|    <span data-ttu-id="64a73-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="64a73-111">Component</span></span>    |                                                                   <span data-ttu-id="64a73-112">なし</span><span class="sxs-lookup"><span data-stu-id="64a73-112">N/A</span></span>                                                                    |
|  <span data-ttu-id="64a73-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="64a73-113">Symbolic Name</span></span>  |                                                       <span data-ttu-id="64a73-114">ENTSSO_E_DTC_IMPORT_FAILED1</span><span class="sxs-lookup"><span data-stu-id="64a73-114">ENTSSO_E_DTC_IMPORT_FAILED1</span></span>                                                        |
|  <span data-ttu-id="64a73-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="64a73-115">Message Text</span></span>   | <span data-ttu-id="64a73-116">DTC トランザクションをインポートできませんでした。</span><span class="sxs-lookup"><span data-stu-id="64a73-116">Could not import a DTC transaction.</span></span> <span data-ttu-id="64a73-117">MSDTC がリモート操作用に正しく構成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="64a73-117">Please check that MSDTC is configured correctly for remote operation.</span></span> <span data-ttu-id="64a73-118">詳細についてはドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="64a73-118">See documentation for details.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="64a73-119">説明</span><span class="sxs-lookup"><span data-stu-id="64a73-119">Explanation</span></span>  
 <span data-ttu-id="64a73-120">DTC トランザクションをインポートできませんでした。</span><span class="sxs-lookup"><span data-stu-id="64a73-120">Could not import a DTC transaction.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="64a73-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="64a73-121">User Action</span></span>  
 <span data-ttu-id="64a73-122">MSDTC がリモート操作用に正しく構成されていることを確認してください。詳細については、指定されたコンピューターのイベント ログを確認してください。</span><span class="sxs-lookup"><span data-stu-id="64a73-122">Check that MSDTC is configured correctly for remote operation, and see the event log on the specified computer for more details.</span></span>  
  
 <span data-ttu-id="64a73-123">MSDTC の問題に関するヘルプは、[MSDTC を使用した問題のトラブルシューティング](../core/troubleshooting-problems-with-msdtc.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64a73-123">For help on MSDTC issues, see [Troubleshooting Problems with MSDTC](../core/troubleshooting-problems-with-msdtc.md).</span></span>
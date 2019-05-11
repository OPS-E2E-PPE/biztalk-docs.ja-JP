---
title: シングル サインオン:イベント 10605 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4c9812b4-43bc-43c4-be8f-6f57c432bda6
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 181191572cd433ebcd6ab2356a1cb0455c6a4c09
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397776"
---
# <a name="single-sign-on-event-10605"></a><span data-ttu-id="df5ad-102">シングル サインオン:イベント 10605</span><span class="sxs-lookup"><span data-stu-id="df5ad-102">Single Sign-On: Event 10605</span></span>
## <a name="details"></a><span data-ttu-id="df5ad-103">詳細</span><span class="sxs-lookup"><span data-stu-id="df5ad-103">Details</span></span>  
  
|                 |                                                                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="df5ad-104">製品名</span><span class="sxs-lookup"><span data-stu-id="df5ad-104">Product Name</span></span>   |                                                                       <span data-ttu-id="df5ad-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="df5ad-105">Enterprise Single Sign-On</span></span>                                                                       |
| <span data-ttu-id="df5ad-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="df5ad-106">Product Version</span></span> |                                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                       |
|    <span data-ttu-id="df5ad-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="df5ad-107">Event ID</span></span>     |                                                                                 <span data-ttu-id="df5ad-108">10605</span><span class="sxs-lookup"><span data-stu-id="df5ad-108">10605</span></span>                                                                                 |
|  <span data-ttu-id="df5ad-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="df5ad-109">Event Source</span></span>   |                                                                                <span data-ttu-id="df5ad-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="df5ad-110">ENTSSO</span></span>                                                                                 |
|    <span data-ttu-id="df5ad-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="df5ad-111">Component</span></span>    |                                                                                  <span data-ttu-id="df5ad-112">なし</span><span class="sxs-lookup"><span data-stu-id="df5ad-112">N/A</span></span>                                                                                  |
|  <span data-ttu-id="df5ad-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="df5ad-113">Symbolic Name</span></span>  |                                                                         <span data-ttu-id="df5ad-114">SSO_ERROR_DTC_IMPORT</span><span class="sxs-lookup"><span data-stu-id="df5ad-114">SSO_ERROR_DTC_IMPORT</span></span>                                                                          |
|  <span data-ttu-id="df5ad-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="df5ad-115">Message Text</span></span>   | <span data-ttu-id="df5ad-116">DTC トランザクションをインポートできませんでした。</span><span class="sxs-lookup"><span data-stu-id="df5ad-116">Could not import a DTC transaction.</span></span> <span data-ttu-id="df5ad-117">MSDTC がリモート操作用に正しく構成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="df5ad-117">Please check that MSDTC is configured correctly for remote operation.</span></span> <span data-ttu-id="df5ad-118">Details.%r のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="df5ad-118">See documentation for details.%r</span></span><br /><br /> <span data-ttu-id="df5ad-119">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="df5ad-119">Error Code: %1</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="df5ad-120">説明</span><span class="sxs-lookup"><span data-stu-id="df5ad-120">Explanation</span></span>  
 <span data-ttu-id="df5ad-121">Microsoft 分散トランザクション コーディネーター (MSDTC) に問題があります。</span><span class="sxs-lookup"><span data-stu-id="df5ad-121">There is a problem with the Microsoft Distributed Transaction Coordinator (MSDTC).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="df5ad-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="df5ad-122">User Action</span></span>  
 <span data-ttu-id="df5ad-123">MSDTC の問題に関するヘルプは、次を参照してください。 [MSDTC を使用した問題のトラブルシューティング](../core/troubleshooting-problems-with-msdtc.md)します。</span><span class="sxs-lookup"><span data-stu-id="df5ad-123">For help on MSDTC issues, see [Troubleshooting Problems with MSDTC](../core/troubleshooting-problems-with-msdtc.md).</span></span>
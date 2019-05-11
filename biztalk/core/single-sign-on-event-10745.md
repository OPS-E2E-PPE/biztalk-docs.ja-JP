---
title: シングル サインオン:イベント 10745 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed630e40-d876-4e90-937e-4d2d54fe9f1a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d75304b54a9ebd2484b36273a165cf8fa1cc998
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395502"
---
# <a name="single-sign-on-event-10745"></a><span data-ttu-id="92fef-102">シングル サインオン:イベント 10745</span><span class="sxs-lookup"><span data-stu-id="92fef-102">Single Sign-On: Event 10745</span></span>
## <a name="details"></a><span data-ttu-id="92fef-103">詳細</span><span class="sxs-lookup"><span data-stu-id="92fef-103">Details</span></span>  

|                 |                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="92fef-104">製品名</span><span class="sxs-lookup"><span data-stu-id="92fef-104">Product Name</span></span>   |                                                          <span data-ttu-id="92fef-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="92fef-105">Enterprise Single Sign-On</span></span>                                                           |
| <span data-ttu-id="92fef-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="92fef-106">Product Version</span></span> |                                          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                          |
|    <span data-ttu-id="92fef-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="92fef-107">Event ID</span></span>     |                                                                    <span data-ttu-id="92fef-108">10745</span><span class="sxs-lookup"><span data-stu-id="92fef-108">10745</span></span>                                                                     |
|  <span data-ttu-id="92fef-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="92fef-109">Event Source</span></span>   |                                                                    <span data-ttu-id="92fef-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="92fef-110">ENTSSO</span></span>                                                                    |
|    <span data-ttu-id="92fef-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="92fef-111">Component</span></span>    |                                                                     <span data-ttu-id="92fef-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="92fef-112">N\A</span></span>                                                                      |
|  <span data-ttu-id="92fef-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="92fef-113">Symbolic Name</span></span>  |                                                          <span data-ttu-id="92fef-114">SSO_ERROR_ADAPTER_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="92fef-114">SSO_ERROR_ADAPTER_OFFLINE</span></span>                                                           |
|  <span data-ttu-id="92fef-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="92fef-115">Message Text</span></span>   | <span data-ttu-id="92fef-116">アダプターが offline.%r</span><span class="sxs-lookup"><span data-stu-id="92fef-116">The adapter is offline.%r</span></span><br /><br /> <span data-ttu-id="92fef-117">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="92fef-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="92fef-118">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="92fef-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="92fef-119">エラー メッセージ: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="92fef-119">Error Message: %3%r</span></span><br /><br /> <span data-ttu-id="92fef-120">エラー コード: %4</span><span class="sxs-lookup"><span data-stu-id="92fef-120">Error Code: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="92fef-121">説明</span><span class="sxs-lookup"><span data-stu-id="92fef-121">Explanation</span></span>  
 <span data-ttu-id="92fef-122">このエラー イベントは、指定されたアダプターがオフラインであることを示します。</span><span class="sxs-lookup"><span data-stu-id="92fef-122">This Error event indicates that the specified adapter is offline.</span></span>  

## <a name="user-action"></a><span data-ttu-id="92fef-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="92fef-123">User Action</span></span>  
 <span data-ttu-id="92fef-124">このエラーを解決するには、以下の 1 つ以上の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="92fef-124">To resolve this error, do one or more of the following:</span></span>  

- <span data-ttu-id="92fef-125">関連付けられているエラーのシステムおよびアプリケーション イベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="92fef-125">Check the system and application event logs for associated errors.</span></span>  

- <span data-ttu-id="92fef-126">外部アダプターでエラーを確認します。</span><span class="sxs-lookup"><span data-stu-id="92fef-126">Check the external adapter for errors.</span></span>  

  <span data-ttu-id="92fef-127">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="92fef-127">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="92fef-128">パスワード同期を管理する方法</span><span class="sxs-lookup"><span data-stu-id="92fef-128">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)

---
title: 'シングル サインオン: イベント 10747 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63ae1ab4-0f4e-45a7-83c1-31b8037e4dd7
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6303d7dd39c2168d67d206401bdf8d2c30f5d21
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993915"
---
# <a name="single-sign-on-event-10747"></a><span data-ttu-id="30203-102">シングル サインオン: イベント 10747</span><span class="sxs-lookup"><span data-stu-id="30203-102">Single Sign-On: Event 10747</span></span>
## <a name="details"></a><span data-ttu-id="30203-103">詳細</span><span class="sxs-lookup"><span data-stu-id="30203-103">Details</span></span>  

|                 |                                                                                                                                        |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="30203-104">製品名</span><span class="sxs-lookup"><span data-stu-id="30203-104">Product Name</span></span>   |                                                       <span data-ttu-id="30203-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="30203-105">Enterprise Single Sign-On</span></span>                                                        |
| <span data-ttu-id="30203-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="30203-106">Product Version</span></span> |                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                       |
|    <span data-ttu-id="30203-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="30203-107">Event ID</span></span>     |                                                                 <span data-ttu-id="30203-108">10747</span><span class="sxs-lookup"><span data-stu-id="30203-108">10747</span></span>                                                                  |
|  <span data-ttu-id="30203-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="30203-109">Event Source</span></span>   |                                                                  <span data-ttu-id="30203-110">N\A</span><span class="sxs-lookup"><span data-stu-id="30203-110">N\A</span></span>                                                                   |
|    <span data-ttu-id="30203-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="30203-111">Component</span></span>    |                                                                  <span data-ttu-id="30203-112">N\A</span><span class="sxs-lookup"><span data-stu-id="30203-112">N\A</span></span>                                                                   |
|  <span data-ttu-id="30203-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="30203-113">Symbolic Name</span></span>  |                                                     <span data-ttu-id="30203-114">SSO_ERROR_UNKNOWN_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="30203-114">SSO_ERROR_UNKNOWN_NOTIFICATION</span></span>                                                     |
|  <span data-ttu-id="30203-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="30203-115">Message Text</span></span>   | <span data-ttu-id="30203-116">不明な通知の種類が受信されました。%r</span><span class="sxs-lookup"><span data-stu-id="30203-116">An unknown notification type was received.%r</span></span><br /><br /> <span data-ttu-id="30203-117">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="30203-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="30203-118">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="30203-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="30203-119">通知の種類: %3</span><span class="sxs-lookup"><span data-stu-id="30203-119">Notification Type: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="30203-120">説明</span><span class="sxs-lookup"><span data-stu-id="30203-120">Explanation</span></span>  
 <span data-ttu-id="30203-121">このエラー イベントは、無効な通知の種類に関する内部エラーが SSO サービスによって検出されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="30203-121">This Error event indicates that an internal error with an invalid notification type was detected by the SSO service.</span></span>  

## <a name="user-action"></a><span data-ttu-id="30203-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="30203-122">User Action</span></span>  
 <span data-ttu-id="30203-123">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="30203-123">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="30203-124">システムおよびアプリケーションのイベント ログで関連するイベントを確認します。</span><span class="sxs-lookup"><span data-stu-id="30203-124">Check the system and application event logs for associated events.</span></span>  

  <span data-ttu-id="30203-125">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="30203-125">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="30203-126">SSO の使用</span><span class="sxs-lookup"><span data-stu-id="30203-126">Using SSO</span></span>](../core/using-sso.md)

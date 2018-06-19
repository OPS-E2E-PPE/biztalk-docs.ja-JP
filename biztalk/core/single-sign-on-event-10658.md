---
title: 'シングル サインオン: イベント 10658 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c5bee12d-502b-4fee-bc84-25807eb0e48e
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9594f2462422190c243d98c165ead37898e33f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271738"
---
# <a name="single-sign-on-event-10658"></a><span data-ttu-id="1a354-102">シングル サインオン: イベント 10658</span><span class="sxs-lookup"><span data-stu-id="1a354-102">Single Sign-On: Event 10658</span></span>
## <a name="details"></a><span data-ttu-id="1a354-103">詳細</span><span class="sxs-lookup"><span data-stu-id="1a354-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1a354-104">製品名</span><span class="sxs-lookup"><span data-stu-id="1a354-104">Product Name</span></span>|<span data-ttu-id="1a354-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="1a354-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="1a354-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="1a354-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="1a354-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="1a354-107">Event ID</span></span>|<span data-ttu-id="1a354-108">10658</span><span class="sxs-lookup"><span data-stu-id="1a354-108">10658</span></span>|  
|<span data-ttu-id="1a354-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="1a354-109">Event Source</span></span>|<span data-ttu-id="1a354-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="1a354-110">ENTSSO</span></span>|  
|<span data-ttu-id="1a354-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1a354-111">Component</span></span>|<span data-ttu-id="1a354-112">N\A</span><span class="sxs-lookup"><span data-stu-id="1a354-112">N\A</span></span>|  
|<span data-ttu-id="1a354-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="1a354-113">Symbolic Name</span></span>|<span data-ttu-id="1a354-114">SSO_ERROR_PASSWORD_SYNC_ADAPTERS_START_FAILED</span><span class="sxs-lookup"><span data-stu-id="1a354-114">SSO_ERROR_PASSWORD_SYNC_ADAPTERS_START_FAILED</span></span>|  
|<span data-ttu-id="1a354-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="1a354-115">Message Text</span></span>|<span data-ttu-id="1a354-116">外部アダプターのパスワード同期を開始できませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="1a354-116">Password sync for external adapters failed to start.%r</span></span><br /><br /> <span data-ttu-id="1a354-117">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="1a354-117">Error Code: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1a354-118">説明</span><span class="sxs-lookup"><span data-stu-id="1a354-118">Explanation</span></span>  
 <span data-ttu-id="1a354-119">このエラー イベントは、外部アダプターのパスワード同期を開始できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="1a354-119">This Error event indicates that password sync for external adapters failed to start.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1a354-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="1a354-120">User Action</span></span>  
 <span data-ttu-id="1a354-121">このエラーを解決するには、以下の 1 つ以上の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a354-121">To resolve this error, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="1a354-122">関連するイベントについては、アプリケーションとシステムのイベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="1a354-122">Check the application and system event logs for associated events.</span></span>  
  
-   <span data-ttu-id="1a354-123">アダプター構成プロパティを確認します。</span><span class="sxs-lookup"><span data-stu-id="1a354-123">Verify adapter configuration properties.</span></span>  

## <a name="more-info"></a><span data-ttu-id="1a354-124">詳細</span><span class="sxs-lookup"><span data-stu-id="1a354-124">More info</span></span>  
  
-   [<span data-ttu-id="1a354-125">パスワード同期を管理する方法</span><span class="sxs-lookup"><span data-stu-id="1a354-125">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)  
  
-   <span data-ttu-id="1a354-126">**エンタープライズ シングル サインオン UI ヘルプ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="1a354-126">**Enterprise Single Sign-On UI Help** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
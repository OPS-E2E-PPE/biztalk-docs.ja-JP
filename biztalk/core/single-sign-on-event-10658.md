---
title: 'シングル サインオン: イベント 10658 |Microsoft Docs'
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
ms.openlocfilehash: dd6ea4cb33e6df4fe8a59fc1041861bdb530aaa4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982251"
---
# <a name="single-sign-on-event-10658"></a><span data-ttu-id="7a877-102">シングル サインオン: イベント 10658</span><span class="sxs-lookup"><span data-stu-id="7a877-102">Single Sign-On: Event 10658</span></span>
## <a name="details"></a><span data-ttu-id="7a877-103">詳細</span><span class="sxs-lookup"><span data-stu-id="7a877-103">Details</span></span>  

|                 |                                                                                   |
|-----------------|-----------------------------------------------------------------------------------|
|  <span data-ttu-id="7a877-104">製品名</span><span class="sxs-lookup"><span data-stu-id="7a877-104">Product Name</span></span>   |                             <span data-ttu-id="7a877-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="7a877-105">Enterprise Single Sign-On</span></span>                             |
| <span data-ttu-id="7a877-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="7a877-106">Product Version</span></span> |            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]             |
|    <span data-ttu-id="7a877-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7a877-107">Event ID</span></span>     |                                       <span data-ttu-id="7a877-108">10658</span><span class="sxs-lookup"><span data-stu-id="7a877-108">10658</span></span>                                       |
|  <span data-ttu-id="7a877-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="7a877-109">Event Source</span></span>   |                                      <span data-ttu-id="7a877-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="7a877-110">ENTSSO</span></span>                                       |
|    <span data-ttu-id="7a877-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7a877-111">Component</span></span>    |                                        <span data-ttu-id="7a877-112">N\A</span><span class="sxs-lookup"><span data-stu-id="7a877-112">N\A</span></span>                                        |
|  <span data-ttu-id="7a877-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="7a877-113">Symbolic Name</span></span>  |                   <span data-ttu-id="7a877-114">SSO_ERROR_PASSWORD_SYNC_ADAPTERS_START_FAILED</span><span class="sxs-lookup"><span data-stu-id="7a877-114">SSO_ERROR_PASSWORD_SYNC_ADAPTERS_START_FAILED</span></span>                   |
|  <span data-ttu-id="7a877-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="7a877-115">Message Text</span></span>   | <span data-ttu-id="7a877-116">外部アダプターのパスワード同期を開始できませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="7a877-116">Password sync for external adapters failed to start.%r</span></span><br /><br /> <span data-ttu-id="7a877-117">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="7a877-117">Error Code: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="7a877-118">説明</span><span class="sxs-lookup"><span data-stu-id="7a877-118">Explanation</span></span>  
 <span data-ttu-id="7a877-119">このエラー イベントは、外部アダプターのパスワード同期を開始できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="7a877-119">This Error event indicates that password sync for external adapters failed to start.</span></span>  

## <a name="user-action"></a><span data-ttu-id="7a877-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="7a877-120">User Action</span></span>  
 <span data-ttu-id="7a877-121">このエラーを解決するには、以下の 1 つ以上の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="7a877-121">To resolve this error, do one or more of the following:</span></span>  

-   <span data-ttu-id="7a877-122">関連するイベントについては、アプリケーションとシステムのイベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="7a877-122">Check the application and system event logs for associated events.</span></span>  

-   <span data-ttu-id="7a877-123">アダプター構成プロパティを確認します。</span><span class="sxs-lookup"><span data-stu-id="7a877-123">Verify adapter configuration properties.</span></span>  

## <a name="more-info"></a><span data-ttu-id="7a877-124">詳細</span><span class="sxs-lookup"><span data-stu-id="7a877-124">More info</span></span>  

- [<span data-ttu-id="7a877-125">パスワード同期を管理する方法</span><span class="sxs-lookup"><span data-stu-id="7a877-125">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)  

- <span data-ttu-id="7a877-126">**エンタープライズ シングル サインオン UI のヘルプ** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="7a877-126">**Enterprise Single Sign-On UI Help** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>

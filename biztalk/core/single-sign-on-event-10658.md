---
title: シングル サインオン:イベント 10658 |Microsoft Docs
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
ms.openlocfilehash: b8ac64b60ba9a4d92452b3299f0e1f30cef192d6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397612"
---
# <a name="single-sign-on-event-10658"></a><span data-ttu-id="a37af-102">シングル サインオン:イベント 10658</span><span class="sxs-lookup"><span data-stu-id="a37af-102">Single Sign-On: Event 10658</span></span>
## <a name="details"></a><span data-ttu-id="a37af-103">詳細</span><span class="sxs-lookup"><span data-stu-id="a37af-103">Details</span></span>  

|                 |                                                                                   |
|-----------------|-----------------------------------------------------------------------------------|
|  <span data-ttu-id="a37af-104">製品名</span><span class="sxs-lookup"><span data-stu-id="a37af-104">Product Name</span></span>   |                             <span data-ttu-id="a37af-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="a37af-105">Enterprise Single Sign-On</span></span>                             |
| <span data-ttu-id="a37af-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="a37af-106">Product Version</span></span> |            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]             |
|    <span data-ttu-id="a37af-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="a37af-107">Event ID</span></span>     |                                       <span data-ttu-id="a37af-108">10658</span><span class="sxs-lookup"><span data-stu-id="a37af-108">10658</span></span>                                       |
|  <span data-ttu-id="a37af-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="a37af-109">Event Source</span></span>   |                                      <span data-ttu-id="a37af-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a37af-110">ENTSSO</span></span>                                       |
|    <span data-ttu-id="a37af-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a37af-111">Component</span></span>    |                                        <span data-ttu-id="a37af-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="a37af-112">N\A</span></span>                                        |
|  <span data-ttu-id="a37af-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="a37af-113">Symbolic Name</span></span>  |                   <span data-ttu-id="a37af-114">SSO_ERROR_PASSWORD_SYNC_ADAPTERS_START_FAILED</span><span class="sxs-lookup"><span data-stu-id="a37af-114">SSO_ERROR_PASSWORD_SYNC_ADAPTERS_START_FAILED</span></span>                   |
|  <span data-ttu-id="a37af-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="a37af-115">Message Text</span></span>   | <span data-ttu-id="a37af-116">Start.%r 外部アダプタのパスワード同期が失敗しました</span><span class="sxs-lookup"><span data-stu-id="a37af-116">Password sync for external adapters failed to start.%r</span></span><br /><br /> <span data-ttu-id="a37af-117">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="a37af-117">Error Code: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="a37af-118">説明</span><span class="sxs-lookup"><span data-stu-id="a37af-118">Explanation</span></span>  
 <span data-ttu-id="a37af-119">このエラー イベントでは、外部アダプターのパスワード同期を開始できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="a37af-119">This Error event indicates that password sync for external adapters failed to start.</span></span>  

## <a name="user-action"></a><span data-ttu-id="a37af-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="a37af-120">User Action</span></span>  
 <span data-ttu-id="a37af-121">このエラーを解決するには、以下の 1 つ以上の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="a37af-121">To resolve this error, do one or more of the following:</span></span>  

-   <span data-ttu-id="a37af-122">アプリケーションとシステムのイベント ログで関連するイベントを確認します。</span><span class="sxs-lookup"><span data-stu-id="a37af-122">Check the application and system event logs for associated events.</span></span>  

-   <span data-ttu-id="a37af-123">アダプター構成プロパティを確認します。</span><span class="sxs-lookup"><span data-stu-id="a37af-123">Verify adapter configuration properties.</span></span>  

## <a name="more-info"></a><span data-ttu-id="a37af-124">詳細情報</span><span class="sxs-lookup"><span data-stu-id="a37af-124">More info</span></span>  

- [<span data-ttu-id="a37af-125">パスワード同期を管理する方法</span><span class="sxs-lookup"><span data-stu-id="a37af-125">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)  

- <span data-ttu-id="a37af-126">**エンタープライズ シングル サインオン UI のヘルプ** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="a37af-126">**Enterprise Single Sign-On UI Help** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>

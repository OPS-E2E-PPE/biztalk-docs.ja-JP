---
title: 'シングル サインオン: イベント 10661 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c3418f37-770d-4021-9341-5dbe99689da6
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b52ec67069951bcda3dee54da96e33ca5145e9e6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998859"
---
# <a name="single-sign-on-event-10661"></a><span data-ttu-id="26cc6-102">シングル サインオン: イベント 10661</span><span class="sxs-lookup"><span data-stu-id="26cc6-102">Single Sign-On: Event 10661</span></span>
## <a name="details"></a><span data-ttu-id="26cc6-103">詳細</span><span class="sxs-lookup"><span data-stu-id="26cc6-103">Details</span></span>  

|                 |                                                                                     |
|-----------------|-------------------------------------------------------------------------------------|
|  <span data-ttu-id="26cc6-104">製品名</span><span class="sxs-lookup"><span data-stu-id="26cc6-104">Product Name</span></span>   |                              <span data-ttu-id="26cc6-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="26cc6-105">Enterprise Single Sign-On</span></span>                              |
| <span data-ttu-id="26cc6-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="26cc6-106">Product Version</span></span> |             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]              |
|    <span data-ttu-id="26cc6-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="26cc6-107">Event ID</span></span>     |                                        <span data-ttu-id="26cc6-108">10661</span><span class="sxs-lookup"><span data-stu-id="26cc6-108">10661</span></span>                                        |
|  <span data-ttu-id="26cc6-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="26cc6-109">Event Source</span></span>   |                                       <span data-ttu-id="26cc6-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="26cc6-110">ENTSSO</span></span>                                        |
|    <span data-ttu-id="26cc6-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="26cc6-111">Component</span></span>    |                                         <span data-ttu-id="26cc6-112">N\A</span><span class="sxs-lookup"><span data-stu-id="26cc6-112">N\A</span></span>                                         |
|  <span data-ttu-id="26cc6-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="26cc6-113">Symbolic Name</span></span>  |                    <span data-ttu-id="26cc6-114">SSO_ERROR_PASSWORD_SYNC_WINDOWS_START_FAILED</span><span class="sxs-lookup"><span data-stu-id="26cc6-114">SSO_ERROR_PASSWORD_SYNC_WINDOWS_START_FAILED</span></span>                     |
|  <span data-ttu-id="26cc6-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="26cc6-115">Message Text</span></span>   | <span data-ttu-id="26cc6-116">(PCNS からの) Windows のパスワード同期を開始できませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="26cc6-116">Password sync for Windows (from PCNS) failed to start.%r</span></span><br /><br /> <span data-ttu-id="26cc6-117">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="26cc6-117">Error Code: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="26cc6-118">説明</span><span class="sxs-lookup"><span data-stu-id="26cc6-118">Explanation</span></span>  
 <span data-ttu-id="26cc6-119">このエラー イベントは、Windows のパスワード同期を開始できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="26cc6-119">This Error event indicates that password sync for Windows failed to start.</span></span>  

## <a name="user-action"></a><span data-ttu-id="26cc6-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="26cc6-120">User Action</span></span>  
 <span data-ttu-id="26cc6-121">このエラーを解決するには、以下の 1 つ以上の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="26cc6-121">To resolve this error, do one or more of the following:</span></span>  

-   <span data-ttu-id="26cc6-122">関連するイベントについては、アプリケーションとシステムのイベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="26cc6-122">Check the application and system event logs for associated events.</span></span>  

-   <span data-ttu-id="26cc6-123">アダプター構成プロパティを確認します。</span><span class="sxs-lookup"><span data-stu-id="26cc6-123">Verify adapter configuration properties.</span></span>  

## <a name="more-info"></a><span data-ttu-id="26cc6-124">詳細</span><span class="sxs-lookup"><span data-stu-id="26cc6-124">More info</span></span>

- [<span data-ttu-id="26cc6-125">パスワード同期を管理する方法</span><span class="sxs-lookup"><span data-stu-id="26cc6-125">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)  

- <span data-ttu-id="26cc6-126">**エンタープライズ シングル サインオン UI のヘルプ** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="26cc6-126">**Enterprise Single Sign-On UI Help** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>

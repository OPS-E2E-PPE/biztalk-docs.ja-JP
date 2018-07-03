---
title: 'シングル サインオン: イベント 10848 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 61888420-29a6-4c64-a884-1b074b586f21
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59a324ff0a5de2ac6d2292692f2132c10aaabc5b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991035"
---
# <a name="single-sign-on-event-10848"></a><span data-ttu-id="abe9e-102">シングル サインオン: イベント 10848</span><span class="sxs-lookup"><span data-stu-id="abe9e-102">Single Sign-On: Event 10848</span></span>
## <a name="details"></a><span data-ttu-id="abe9e-103">詳細</span><span class="sxs-lookup"><span data-stu-id="abe9e-103">Details</span></span>  
  
|                 |                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------|
|  <span data-ttu-id="abe9e-104">製品名</span><span class="sxs-lookup"><span data-stu-id="abe9e-104">Product Name</span></span>   |                                 <span data-ttu-id="abe9e-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="abe9e-105">Enterprise Single Sign-On</span></span>                                  |
| <span data-ttu-id="abe9e-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="abe9e-106">Product Version</span></span> |                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                 |
|    <span data-ttu-id="abe9e-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="abe9e-107">Event ID</span></span>     |                                           <span data-ttu-id="abe9e-108">10848</span><span class="sxs-lookup"><span data-stu-id="abe9e-108">10848</span></span>                                            |
|  <span data-ttu-id="abe9e-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="abe9e-109">Event Source</span></span>   |                                           <span data-ttu-id="abe9e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="abe9e-110">ENTSSO</span></span>                                           |
|    <span data-ttu-id="abe9e-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="abe9e-111">Component</span></span>    |                                            <span data-ttu-id="abe9e-112">なし</span><span class="sxs-lookup"><span data-stu-id="abe9e-112">N/A</span></span>                                             |
|  <span data-ttu-id="abe9e-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="abe9e-113">Symbolic Name</span></span>  |                         <span data-ttu-id="abe9e-114">ENTSSO_E_DIRECT_SYNC_NOT_ALLOWED_AMBIGUOUS</span><span class="sxs-lookup"><span data-stu-id="abe9e-114">ENTSSO_E_DIRECT_SYNC_NOT_ALLOWED_AMBIGUOUS</span></span>                         |
|  <span data-ttu-id="abe9e-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="abe9e-115">Message Text</span></span>   | <span data-ttu-id="abe9e-116">直接パスワード同期は、そのフィールドがあいまいなため、このアプリケーションは許可されません。</span><span class="sxs-lookup"><span data-stu-id="abe9e-116">Direct password sync is not allowed for this application because its fields are ambiguous.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="abe9e-117">説明</span><span class="sxs-lookup"><span data-stu-id="abe9e-117">Explanation</span></span>  
 <span data-ttu-id="abe9e-118">フィールドが 2 つ以上ある場合、パスワードの同期を設定できるのは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="abe9e-118">If there are more than two fields, then one and only one must be marked for password sync.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="abe9e-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="abe9e-119">User Action</span></span>  
 <span data-ttu-id="abe9e-120">この状況を解決するために、アプリケーションをいったん削除し、これらのガイドラインに沿って再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abe9e-120">To remedy this situation, you must delete the application and recreate it so that it follows these guidelines.</span></span>
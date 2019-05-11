---
title: シングル サインオン:イベント 11014 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71e4c9bd-8bda-46ca-9e76-f7b4fa033167
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aebd0225967e3165f19449b73488d8f938b349ef
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267275"
---
# <a name="single-sign-on-event-11014"></a><span data-ttu-id="04e61-102">シングル サインオン:イベント 11014</span><span class="sxs-lookup"><span data-stu-id="04e61-102">Single Sign-On: Event 11014</span></span>
## <a name="details"></a><span data-ttu-id="04e61-103">詳細</span><span class="sxs-lookup"><span data-stu-id="04e61-103">Details</span></span>  
  
|                 |                                                                                                                                                          |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="04e61-104">製品名</span><span class="sxs-lookup"><span data-stu-id="04e61-104">Product Name</span></span>   |                                                                <span data-ttu-id="04e61-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="04e61-105">Enterprise Single Sign-On</span></span>                                                                 |
| <span data-ttu-id="04e61-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="04e61-106">Product Version</span></span> |                                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                |
|    <span data-ttu-id="04e61-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="04e61-107">Event ID</span></span>     |                                                                          <span data-ttu-id="04e61-108">11014</span><span class="sxs-lookup"><span data-stu-id="04e61-108">11014</span></span>                                                                           |
|  <span data-ttu-id="04e61-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="04e61-109">Event Source</span></span>   |                                                                          <span data-ttu-id="04e61-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="04e61-110">ENTSSO</span></span>                                                                          |
|    <span data-ttu-id="04e61-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="04e61-111">Component</span></span>    |                                                                           <span data-ttu-id="04e61-112">なし</span><span class="sxs-lookup"><span data-stu-id="04e61-112">N/A</span></span>                                                                            |
|  <span data-ttu-id="04e61-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="04e61-113">Symbolic Name</span></span>  |                                                                  <span data-ttu-id="04e61-114">SSO_ERROR_ACCESS_CHECK</span><span class="sxs-lookup"><span data-stu-id="04e61-114">SSO_ERROR_ACCESS_CHECK</span></span>                                                                  |
|  <span data-ttu-id="04e61-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="04e61-115">Message Text</span></span>   | <span data-ttu-id="04e61-116">アクセス チェック failed.%r</span><span class="sxs-lookup"><span data-stu-id="04e61-116">Access check failed.%r</span></span><br /><br /> <span data-ttu-id="04e61-117">クライアント ユーザー: %1\\% 2 %r</span><span class="sxs-lookup"><span data-stu-id="04e61-117">Client User: %1\\%2%r</span></span><br /><br /> <span data-ttu-id="04e61-118">アプリケーション名: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="04e61-118">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="04e61-119">追加データ: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="04e61-119">Additional Data: %4%r</span></span><br /><br /> <span data-ttu-id="04e61-120">エラー コード: %5</span><span class="sxs-lookup"><span data-stu-id="04e61-120">Error Code: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="04e61-121">説明</span><span class="sxs-lookup"><span data-stu-id="04e61-121">Explanation</span></span>  
 <span data-ttu-id="04e61-122">クライアントと表示されているアプリケーションのアクセス チェックが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="04e61-122">The access check failed for the client and application listed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="04e61-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="04e61-123">User Action</span></span>  
 <span data-ttu-id="04e61-124">追加の情報には、問題を修正することが有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="04e61-124">The additional information should enable you to fix the problem.</span></span> <span data-ttu-id="04e61-125">このエラーを回避するために、将来、減らすことができますも監査レベル。</span><span class="sxs-lookup"><span data-stu-id="04e61-125">To avoid this error in the future, you can also lower the audit level.</span></span>
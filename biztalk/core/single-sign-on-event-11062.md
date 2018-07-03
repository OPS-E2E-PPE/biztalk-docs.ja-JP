---
title: 'シングル サインオン: イベント 11062 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55c7c2ea-c671-4853-ac64-8cb80bba98b0
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50df4834f92eff7cc679c051f529f4dbaefc4335
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970143"
---
# <a name="single-sign-on-event-11062"></a><span data-ttu-id="42305-102">シングル サインオン: イベント 11062</span><span class="sxs-lookup"><span data-stu-id="42305-102">Single Sign-On: Event 11062</span></span>
## <a name="details"></a><span data-ttu-id="42305-103">詳細</span><span class="sxs-lookup"><span data-stu-id="42305-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="42305-104">製品名</span><span class="sxs-lookup"><span data-stu-id="42305-104">Product Name</span></span>   |                                                                                       <span data-ttu-id="42305-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="42305-105">Enterprise Single Sign-On</span></span>                                                                                        |
| <span data-ttu-id="42305-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="42305-106">Product Version</span></span> |                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                       |
|    <span data-ttu-id="42305-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="42305-107">Event ID</span></span>     |                                                                                                 <span data-ttu-id="42305-108">11062</span><span class="sxs-lookup"><span data-stu-id="42305-108">11062</span></span>                                                                                                  |
|  <span data-ttu-id="42305-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="42305-109">Event Source</span></span>   |                                                                                                 <span data-ttu-id="42305-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="42305-110">ENTSSO</span></span>                                                                                                 |
|    <span data-ttu-id="42305-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="42305-111">Component</span></span>    |                                                                                                  <span data-ttu-id="42305-112">なし</span><span class="sxs-lookup"><span data-stu-id="42305-112">N/A</span></span>                                                                                                   |
|  <span data-ttu-id="42305-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="42305-113">Symbolic Name</span></span>  |                                                                                    <span data-ttu-id="42305-114">SSO_WARN_PASSWORD_FILTER_FAILED</span><span class="sxs-lookup"><span data-stu-id="42305-114">SSO_WARN_PASSWORD_FILTER_FAILED</span></span>                                                                                     |
|  <span data-ttu-id="42305-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="42305-115">Message Text</span></span>   | <span data-ttu-id="42305-116">パスワードのフィルター処理が失敗しました。</span><span class="sxs-lookup"><span data-stu-id="42305-116">Password filtering failed.</span></span> <span data-ttu-id="42305-117">パスワード フィルターは使用されません。%r</span><span class="sxs-lookup"><span data-stu-id="42305-117">No password filter will be used.%r</span></span><br /><br /> <span data-ttu-id="42305-118">アプリケーション名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="42305-118">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="42305-119">パスワード フィルタ文字列: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="42305-119">Password Filter String: %2%r</span></span><br /><br /> <span data-ttu-id="42305-120">追加データ: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="42305-120">Additional Data: %3%r</span></span><br /><br /> <span data-ttu-id="42305-121">エラー コード: %4</span><span class="sxs-lookup"><span data-stu-id="42305-121">Error Code: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="42305-122">説明</span><span class="sxs-lookup"><span data-stu-id="42305-122">Explanation</span></span>  
 <span data-ttu-id="42305-123">パスワード フィルターの作成中にエラーが発生し、フィルターは作成されませんでした。</span><span class="sxs-lookup"><span data-stu-id="42305-123">An error occurred while creating a password filter, and the filter was not created.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="42305-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="42305-124">User Action</span></span>  
 <span data-ttu-id="42305-125">パスワード フィルターの作成ウィザードを使用して、パスワード フィルターを作成するを参照してください。[パスワード フィルターを使用する方法](../core/how-to-use-password-filters.md)します。</span><span class="sxs-lookup"><span data-stu-id="42305-125">To create the Password Filter using the Create Password Filter Wizard, see [How to Use Password Filters](../core/how-to-use-password-filters.md).</span></span>
---
title: シングル サインオン:イベント 11062 |Microsoft Docs
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
ms.openlocfilehash: 968ae902025e20d11aa4476cf13e22d116650088
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258671"
---
# <a name="single-sign-on-event-11062"></a><span data-ttu-id="6d39f-102">シングル サインオン:イベント 11062</span><span class="sxs-lookup"><span data-stu-id="6d39f-102">Single Sign-On: Event 11062</span></span>
## <a name="details"></a><span data-ttu-id="6d39f-103">詳細</span><span class="sxs-lookup"><span data-stu-id="6d39f-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="6d39f-104">製品名</span><span class="sxs-lookup"><span data-stu-id="6d39f-104">Product Name</span></span>   |                                                                                       <span data-ttu-id="6d39f-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="6d39f-105">Enterprise Single Sign-On</span></span>                                                                                        |
| <span data-ttu-id="6d39f-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="6d39f-106">Product Version</span></span> |                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                       |
|    <span data-ttu-id="6d39f-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="6d39f-107">Event ID</span></span>     |                                                                                                 <span data-ttu-id="6d39f-108">11062</span><span class="sxs-lookup"><span data-stu-id="6d39f-108">11062</span></span>                                                                                                  |
|  <span data-ttu-id="6d39f-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="6d39f-109">Event Source</span></span>   |                                                                                                 <span data-ttu-id="6d39f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="6d39f-110">ENTSSO</span></span>                                                                                                 |
|    <span data-ttu-id="6d39f-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6d39f-111">Component</span></span>    |                                                                                                  <span data-ttu-id="6d39f-112">なし</span><span class="sxs-lookup"><span data-stu-id="6d39f-112">N/A</span></span>                                                                                                   |
|  <span data-ttu-id="6d39f-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="6d39f-113">Symbolic Name</span></span>  |                                                                                    <span data-ttu-id="6d39f-114">SSO_WARN_PASSWORD_FILTER_FAILED</span><span class="sxs-lookup"><span data-stu-id="6d39f-114">SSO_WARN_PASSWORD_FILTER_FAILED</span></span>                                                                                     |
|  <span data-ttu-id="6d39f-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="6d39f-115">Message Text</span></span>   | <span data-ttu-id="6d39f-116">パスワードのフィルター処理に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="6d39f-116">Password filtering failed.</span></span> <span data-ttu-id="6d39f-117">パスワード フィルターが used.%r はありません。</span><span class="sxs-lookup"><span data-stu-id="6d39f-117">No password filter will be used.%r</span></span><br /><br /> <span data-ttu-id="6d39f-118">アプリケーション名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="6d39f-118">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="6d39f-119">パスワード フィルタ文字列: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="6d39f-119">Password Filter String: %2%r</span></span><br /><br /> <span data-ttu-id="6d39f-120">追加データ: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="6d39f-120">Additional Data: %3%r</span></span><br /><br /> <span data-ttu-id="6d39f-121">エラー コード: %4</span><span class="sxs-lookup"><span data-stu-id="6d39f-121">Error Code: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="6d39f-122">説明</span><span class="sxs-lookup"><span data-stu-id="6d39f-122">Explanation</span></span>  
 <span data-ttu-id="6d39f-123">パスワード フィルターの作成中にエラーが発生しました。 および、フィルターは作成されませんでした。</span><span class="sxs-lookup"><span data-stu-id="6d39f-123">An error occurred while creating a password filter, and the filter was not created.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6d39f-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="6d39f-124">User Action</span></span>  
 <span data-ttu-id="6d39f-125">パスワード フィルターの作成ウィザードを使用して、パスワード フィルターを作成するを参照してください。[パスワード フィルターを使用する方法](../core/how-to-use-password-filters.md)します。</span><span class="sxs-lookup"><span data-stu-id="6d39f-125">To create the Password Filter using the Create Password Filter Wizard, see [How to Use Password Filters](../core/how-to-use-password-filters.md).</span></span>
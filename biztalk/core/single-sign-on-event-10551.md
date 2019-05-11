---
title: シングル サインオン:イベント 10551 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33434989-08d8-4d13-a3cc-4c5543add69c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87e1965abac7bf861cfc90cfb2981b5ac30bd5b9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65250257"
---
# <a name="single-sign-on-event-10551"></a><span data-ttu-id="50b8d-102">シングル サインオン:イベント 10551</span><span class="sxs-lookup"><span data-stu-id="50b8d-102">Single Sign-On: Event 10551</span></span>
## <a name="details"></a><span data-ttu-id="50b8d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="50b8d-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="50b8d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="50b8d-104">Product Name</span></span>   |                                                                                                   <span data-ttu-id="50b8d-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="50b8d-105">Enterprise Single Sign-On</span></span>                                                                                                   |
| <span data-ttu-id="50b8d-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="50b8d-106">Product Version</span></span> |                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                   |
|    <span data-ttu-id="50b8d-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="50b8d-107">Event ID</span></span>     |                                                                                                             <span data-ttu-id="50b8d-108">10551</span><span class="sxs-lookup"><span data-stu-id="50b8d-108">10551</span></span>                                                                                                             |
|  <span data-ttu-id="50b8d-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="50b8d-109">Event Source</span></span>   |                                                                                                            <span data-ttu-id="50b8d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="50b8d-110">ENTSSO</span></span>                                                                                                             |
|    <span data-ttu-id="50b8d-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="50b8d-111">Component</span></span>    |                                                                                                              <span data-ttu-id="50b8d-112">なし</span><span class="sxs-lookup"><span data-stu-id="50b8d-112">N/A</span></span>                                                                                                              |
|  <span data-ttu-id="50b8d-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="50b8d-113">Symbolic Name</span></span>  |                                                                                                     <span data-ttu-id="50b8d-114">SSO_WARN_INVALID_USER</span><span class="sxs-lookup"><span data-stu-id="50b8d-114">SSO_WARN_INVALID_USER</span></span>                                                                                                     |
|  <span data-ttu-id="50b8d-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="50b8d-115">Message Text</span></span>   | <span data-ttu-id="50b8d-116">指定したユーザーがこの application.%r 無効なために、マッピングを作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="50b8d-116">A mapping could not be created because the specified user is not valid for this application.%r</span></span><br /><br /> <span data-ttu-id="50b8d-117">ドメイン名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="50b8d-117">Domain Name: %1%r</span></span><br /><br /> <span data-ttu-id="50b8d-118">ユーザー名: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="50b8d-118">User Name: %2%r</span></span><br /><br /> <span data-ttu-id="50b8d-119">アプリケーション名: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="50b8d-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="50b8d-120">アプリケーション ユーザー: %4</span><span class="sxs-lookup"><span data-stu-id="50b8d-120">Application Users: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="50b8d-121">説明</span><span class="sxs-lookup"><span data-stu-id="50b8d-121">Explanation</span></span>  
 <span data-ttu-id="50b8d-122">指定したユーザーが無効です。</span><span class="sxs-lookup"><span data-stu-id="50b8d-122">The specified user is not valid.</span></span> <span data-ttu-id="50b8d-123">これは、入力エラーである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="50b8d-123">This could be a typing error.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="50b8d-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="50b8d-124">User Action</span></span>  
 <span data-ttu-id="50b8d-125">警告情報にリストされているユーザー名を修正して、マッピングを作成し、あることを確認するもう一度です。</span><span class="sxs-lookup"><span data-stu-id="50b8d-125">Check the User Name listed in the warning information, confirm that it is correct, and then create the mapping again.</span></span>
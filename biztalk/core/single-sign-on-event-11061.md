---
title: 'シングル サインオン: イベント 11061 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52fb18e2-4482-4cdb-b8ed-d579a95acd7c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1733e444ecdfdaf54b20beb2de6894ade3466f4c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011331"
---
# <a name="single-sign-on-event-11061"></a><span data-ttu-id="94729-102">シングル サインオン: イベント 11061</span><span class="sxs-lookup"><span data-stu-id="94729-102">Single Sign-On: Event 11061</span></span>
## <a name="details"></a><span data-ttu-id="94729-103">詳細</span><span class="sxs-lookup"><span data-stu-id="94729-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="94729-104">製品名</span><span class="sxs-lookup"><span data-stu-id="94729-104">Product Name</span></span>   |                                                                                                                     <span data-ttu-id="94729-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="94729-105">Enterprise Single Sign-On</span></span>                                                                                                                     |
| <span data-ttu-id="94729-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="94729-106">Product Version</span></span> |                                                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                     |
|    <span data-ttu-id="94729-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="94729-107">Event ID</span></span>     |                                                                                                                               <span data-ttu-id="94729-108">11061</span><span class="sxs-lookup"><span data-stu-id="94729-108">11061</span></span>                                                                                                                               |
|  <span data-ttu-id="94729-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="94729-109">Event Source</span></span>   |                                                                                                                              <span data-ttu-id="94729-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="94729-110">ENTSSO</span></span>                                                                                                                               |
|    <span data-ttu-id="94729-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="94729-111">Component</span></span>    |                                                                                                                                <span data-ttu-id="94729-112">なし</span><span class="sxs-lookup"><span data-stu-id="94729-112">N/A</span></span>                                                                                                                                |
|  <span data-ttu-id="94729-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="94729-113">Symbolic Name</span></span>  |                                                                                                                   <span data-ttu-id="94729-114">SSO_WARN_BAD_PASSWORD_FILTER</span><span class="sxs-lookup"><span data-stu-id="94729-114">SSO_WARN_BAD_PASSWORD_FILTER</span></span>                                                                                                                    |
|  <span data-ttu-id="94729-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="94729-115">Message Text</span></span>   | <span data-ttu-id="94729-116">パスワード フィルター文字列が有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="94729-116">The password filter string is not valid.</span></span> <span data-ttu-id="94729-117">パスワード フィルターは使用されません。%r</span><span class="sxs-lookup"><span data-stu-id="94729-117">No password filter will be used.%r</span></span><br /><br /> <span data-ttu-id="94729-118">アプリケーション名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="94729-118">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="94729-119">パスワード フィルタ文字列: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="94729-119">Password Filter String: %2%r</span></span><br /><br /> <span data-ttu-id="94729-120">処理されたトークンの数: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="94729-120">Number Of Tokens Processed: %3%r</span></span><br /><br /> <span data-ttu-id="94729-121">追加データ: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="94729-121">Additional Data: %4%r</span></span><br /><br /> <span data-ttu-id="94729-122">エラー コード: %5</span><span class="sxs-lookup"><span data-stu-id="94729-122">Error Code: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="94729-123">説明</span><span class="sxs-lookup"><span data-stu-id="94729-123">Explanation</span></span>  
 <span data-ttu-id="94729-124">無効なパスワード フィルターが手動で作成されました。</span><span class="sxs-lookup"><span data-stu-id="94729-124">An invalid password filter has been created manually.</span></span> <span data-ttu-id="94729-125">このプロセスの途中で、エラーが発生しました (エラーの場所については、警告テキストの "パスワード フィルター文字列" を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="94729-125">At some point in this process an error was introduced (see Password Filter String in the warning text for the location of the error).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="94729-126">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="94729-126">User Action</span></span>  
 <span data-ttu-id="94729-127">パスワード フィルターの作成ウィザードを使用して、パスワード フィルターを作成するを参照してください。[パスワード フィルターを使用する方法](../core/how-to-use-password-filters.md)します。</span><span class="sxs-lookup"><span data-stu-id="94729-127">To create the Password Filter using the Create Password Filter Wizard, see [How to Use Password Filters](../core/how-to-use-password-filters.md).</span></span>
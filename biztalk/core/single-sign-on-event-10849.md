---
title: 'シングル サインオン: イベント 10849 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fdfb1cea-e445-4318-9891-b6b70a266ca9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cb1d63cf12c19a8e2213c7506f1752f86a02a85
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991851"
---
# <a name="single-sign-on-event-10849"></a><span data-ttu-id="96d94-102">シングル サインオン: イベント 10849</span><span class="sxs-lookup"><span data-stu-id="96d94-102">Single Sign-On: Event 10849</span></span>
## <a name="details"></a><span data-ttu-id="96d94-103">詳細</span><span class="sxs-lookup"><span data-stu-id="96d94-103">Details</span></span>  
  
|                 |                                                                                  |
|-----------------|----------------------------------------------------------------------------------|
|  <span data-ttu-id="96d94-104">製品名</span><span class="sxs-lookup"><span data-stu-id="96d94-104">Product Name</span></span>   |                            <span data-ttu-id="96d94-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="96d94-105">Enterprise Single Sign-On</span></span>                             |
| <span data-ttu-id="96d94-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="96d94-106">Product Version</span></span> |            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]            |
|    <span data-ttu-id="96d94-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="96d94-107">Event ID</span></span>     |                                      <span data-ttu-id="96d94-108">10849</span><span class="sxs-lookup"><span data-stu-id="96d94-108">10849</span></span>                                       |
|  <span data-ttu-id="96d94-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="96d94-109">Event Source</span></span>   |                                      <span data-ttu-id="96d94-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="96d94-110">ENTSSO</span></span>                                      |
|    <span data-ttu-id="96d94-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="96d94-111">Component</span></span>    |                                       <span data-ttu-id="96d94-112">なし</span><span class="sxs-lookup"><span data-stu-id="96d94-112">N/A</span></span>                                        |
|  <span data-ttu-id="96d94-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="96d94-113">Symbolic Name</span></span>  |                     <span data-ttu-id="96d94-114">ENTSSO_E_DIRECT_SYNC_NOT_ALLOWED_CREATE</span><span class="sxs-lookup"><span data-stu-id="96d94-114">ENTSSO_E_DIRECT_SYNC_NOT_ALLOWED_CREATE</span></span>                      |
|  <span data-ttu-id="96d94-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="96d94-115">Message Text</span></span>   | <span data-ttu-id="96d94-116">‘直接パスワード同期’ フラグを指定してアプリケーションを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="96d94-116">An application cannot be created with the ‘direct password sync’ flag specified.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="96d94-117">説明</span><span class="sxs-lookup"><span data-stu-id="96d94-117">Explanation</span></span>  
 <span data-ttu-id="96d94-118">‘直接パスワード同期’ フラグを指定してアプリケーションを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="96d94-118">An application cannot be created with the ‘direct password sync’ flag specified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="96d94-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="96d94-119">User Action</span></span>  
 <span data-ttu-id="96d94-120">直接パスワード同期フラグを設定しないでアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="96d94-120">Create the application without the direct password sync flag.</span></span> <span data-ttu-id="96d94-121">その後、フィールドを追加および作成し、アプリケーションを有効にして、直接パスワード同期フラグを指定します。</span><span class="sxs-lookup"><span data-stu-id="96d94-121">Then add and create the fields, enable the application, and specify the direct password sync flag.</span></span>
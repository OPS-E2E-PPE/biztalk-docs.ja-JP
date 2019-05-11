---
title: シングル サインオン:イベント 10728 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f579189c-c9a5-4d2c-a3d5-f0ba03c5a3ef
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9c7469a60ba0143f3e6674f5b140a452eebfe63
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394335"
---
# <a name="single-sign-on-event-10728"></a><span data-ttu-id="239b8-102">シングル サインオン:イベント 10728</span><span class="sxs-lookup"><span data-stu-id="239b8-102">Single Sign-On: Event 10728</span></span>
## <a name="details"></a><span data-ttu-id="239b8-103">詳細</span><span class="sxs-lookup"><span data-stu-id="239b8-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="239b8-104">製品名</span><span class="sxs-lookup"><span data-stu-id="239b8-104">Product Name</span></span>   |                                                                                                                     <span data-ttu-id="239b8-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="239b8-105">Enterprise Single Sign-On</span></span>                                                                                                                     |
| <span data-ttu-id="239b8-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="239b8-106">Product Version</span></span> |                                                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                     |
|    <span data-ttu-id="239b8-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="239b8-107">Event ID</span></span>     |                                                                                                                               <span data-ttu-id="239b8-108">10728</span><span class="sxs-lookup"><span data-stu-id="239b8-108">10728</span></span>                                                                                                                               |
|  <span data-ttu-id="239b8-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="239b8-109">Event Source</span></span>   |                                                                                                                              <span data-ttu-id="239b8-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="239b8-110">ENTSSO</span></span>                                                                                                                               |
|    <span data-ttu-id="239b8-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="239b8-111">Component</span></span>    |                                                                                                                                <span data-ttu-id="239b8-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="239b8-112">N\A</span></span>                                                                                                                                |
|  <span data-ttu-id="239b8-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="239b8-113">Symbolic Name</span></span>  |                                                                                                                         <span data-ttu-id="239b8-114">SSO_ERROR_VERSION</span><span class="sxs-lookup"><span data-stu-id="239b8-114">SSO_ERROR_VERSION</span></span>                                                                                                                         |
|  <span data-ttu-id="239b8-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="239b8-115">Message Text</span></span>   | <span data-ttu-id="239b8-116">このバージョンの SSO サーバーは、SSO データベースとの互換性がありません。</span><span class="sxs-lookup"><span data-stu-id="239b8-116">This version of the SSO server is not compatible with the SSO database.</span></span> <span data-ttu-id="239b8-117">マスター シークレット server.%r をアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="239b8-117">Please upgrade your master secret server.%r</span></span><br /><br /> <span data-ttu-id="239b8-118">SQL Server 名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="239b8-118">SQL Server Name: %1%r</span></span><br /><br /> <span data-ttu-id="239b8-119">SSO データベース名: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="239b8-119">SSO Database Name: %2%r</span></span><br /><br /> <span data-ttu-id="239b8-120">SSO データベースのバージョン: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="239b8-120">SSO Database Version: %3%r</span></span><br /><br /> <span data-ttu-id="239b8-121">ために必要なバージョン: %4</span><span class="sxs-lookup"><span data-stu-id="239b8-121">Required Version: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="239b8-122">説明</span><span class="sxs-lookup"><span data-stu-id="239b8-122">Explanation</span></span>  
 <span data-ttu-id="239b8-123">このエラー イベントは、SSO サーバーのバージョンが (最初に作成されたバージョン) よりも新しいことを示します、SSO データベース。</span><span class="sxs-lookup"><span data-stu-id="239b8-123">This Error event indicates that the SSO server version is more recent than (the version that originally created) the SSO database.</span></span>  

## <a name="user-action"></a><span data-ttu-id="239b8-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="239b8-124">User Action</span></span>  
 <span data-ttu-id="239b8-125">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="239b8-125">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="239b8-126">この SSO サーバーの現在のバージョンと一致する SSO マスタ シークレット サーバーをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="239b8-126">Upgrade the SSO master secret server to match the current version of this SSO server.</span></span> <span data-ttu-id="239b8-127">これにより、SSO データベースが、現在のバージョンにアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="239b8-127">This will upgrade the SSO database to the current version.</span></span>  

  <span data-ttu-id="239b8-128">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="239b8-128">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="239b8-129">マスター シークレットの管理</span><span class="sxs-lookup"><span data-stu-id="239b8-129">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)

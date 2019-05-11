---
title: シングル サインオン:イベント 11047 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa4eb1ae-45a6-4e0c-9af6-6bf1ed63acfb
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97d70d94ffad94b4a81d09c821469c4adbfbe775
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400957"
---
# <a name="single-sign-on-event-11047"></a><span data-ttu-id="edd64-102">シングル サインオン:イベント 11047</span><span class="sxs-lookup"><span data-stu-id="edd64-102">Single Sign-On: Event 11047</span></span>
## <a name="details"></a><span data-ttu-id="edd64-103">詳細</span><span class="sxs-lookup"><span data-stu-id="edd64-103">Details</span></span>  
  
|                 |                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="edd64-104">製品名</span><span class="sxs-lookup"><span data-stu-id="edd64-104">Product Name</span></span>   |                                                                <span data-ttu-id="edd64-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="edd64-105">Enterprise Single Sign-On</span></span>                                                                |
| <span data-ttu-id="edd64-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="edd64-106">Product Version</span></span> |                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                |
|    <span data-ttu-id="edd64-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="edd64-107">Event ID</span></span>     |                                                                          <span data-ttu-id="edd64-108">11047</span><span class="sxs-lookup"><span data-stu-id="edd64-108">11047</span></span>                                                                          |
|  <span data-ttu-id="edd64-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="edd64-109">Event Source</span></span>   |                                                                         <span data-ttu-id="edd64-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="edd64-110">ENTSSO</span></span>                                                                          |
|    <span data-ttu-id="edd64-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="edd64-111">Component</span></span>    |                                                                           <span data-ttu-id="edd64-112">なし</span><span class="sxs-lookup"><span data-stu-id="edd64-112">N/A</span></span>                                                                           |
|  <span data-ttu-id="edd64-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="edd64-113">Symbolic Name</span></span>  |                                                                 <span data-ttu-id="edd64-114">SSO_ERROR_SSOSQL_FAILED</span><span class="sxs-lookup"><span data-stu-id="edd64-114">SSO_ERROR_SSOSQL_FAILED</span></span>                                                                 |
|  <span data-ttu-id="edd64-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="edd64-115">Message Text</span></span>   | <span data-ttu-id="edd64-116">SSOSQL を作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="edd64-116">Could not create SSOSQL.</span></span> <span data-ttu-id="edd64-117">問題を解決するには、SSO を再インストールするか、Visual Studio コマンド prompt.%r から 'regasm Ssosql.dll' を試してみる</span><span class="sxs-lookup"><span data-stu-id="edd64-117">To fix the problem, reinstall SSO or try ‘regasm SSOSQL.dll’ from a Visual Studio command prompt.%r</span></span><br /><br /> <span data-ttu-id="edd64-118">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="edd64-118">Error Code: %1</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="edd64-119">説明</span><span class="sxs-lookup"><span data-stu-id="edd64-119">Explanation</span></span>  
 <span data-ttu-id="edd64-120">可能性があります、これは、インストール エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="edd64-120">This is likely caused by an installation error.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="edd64-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="edd64-121">User Action</span></span>  
 <span data-ttu-id="edd64-122">問題を解決するには、SSO を再インストールするか、Visual Studio コマンド プロンプトで 'regasm Ssosql.dll' をお試しいただけます。</span><span class="sxs-lookup"><span data-stu-id="edd64-122">To fix the problem, reinstall SSO or try ‘regasm SSOSQL.dll’ from a Visual Studio command prompt.</span></span>
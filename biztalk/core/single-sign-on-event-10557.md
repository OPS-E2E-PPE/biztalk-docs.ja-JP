---
title: 'シングル サインオン: イベント 10557 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f29bc394-4c56-4ded-93a1-004afb3a054a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afc65dba8760c85ad9eb6552e56e52cc6b7dd3ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269770"
---
# <a name="single-sign-on-event-10557"></a><span data-ttu-id="67dc5-102">シングル サインオン: イベント 10557</span><span class="sxs-lookup"><span data-stu-id="67dc5-102">Single Sign-On: Event 10557</span></span>
## <a name="details"></a><span data-ttu-id="67dc5-103">詳細</span><span class="sxs-lookup"><span data-stu-id="67dc5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="67dc5-104">製品名</span><span class="sxs-lookup"><span data-stu-id="67dc5-104">Product Name</span></span>|<span data-ttu-id="67dc5-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="67dc5-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="67dc5-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="67dc5-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="67dc5-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="67dc5-107">Event ID</span></span>|<span data-ttu-id="67dc5-108">10557</span><span class="sxs-lookup"><span data-stu-id="67dc5-108">10557</span></span>|  
|<span data-ttu-id="67dc5-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="67dc5-109">Event Source</span></span>|<span data-ttu-id="67dc5-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="67dc5-110">ENTSSO</span></span>|  
|<span data-ttu-id="67dc5-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="67dc5-111">Component</span></span>|<span data-ttu-id="67dc5-112">なし</span><span class="sxs-lookup"><span data-stu-id="67dc5-112">N/A</span></span>|  
|<span data-ttu-id="67dc5-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="67dc5-113">Symbolic Name</span></span>|<span data-ttu-id="67dc5-114">SSO_WARN_USER_NOT_ALLOWED_FOR_GROUPS</span><span class="sxs-lookup"><span data-stu-id="67dc5-114">SSO_WARN_USER_NOT_ALLOWED_FOR_GROUPS</span></span>|  
|<span data-ttu-id="67dc5-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="67dc5-115">Message Text</span></span>|<span data-ttu-id="67dc5-116">アプリケーション ユーザーはグループ アプリケーションのマッピングの制御を許可されていません。%r</span><span class="sxs-lookup"><span data-stu-id="67dc5-116">Application Users are not allowed to control mappings for Group applications.%r</span></span><br /><br /> <span data-ttu-id="67dc5-117">ドメイン名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="67dc5-117">Domain Name: %1%r</span></span><br /><br /> <span data-ttu-id="67dc5-118">ユーザー名: %2 %r</span><span class="sxs-lookup"><span data-stu-id="67dc5-118">User Name: %2%r</span></span><br /><br /> <span data-ttu-id="67dc5-119">アプリケーション名: %3 %r</span><span class="sxs-lookup"><span data-stu-id="67dc5-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="67dc5-120">クライアント ユーザー: %4</span><span class="sxs-lookup"><span data-stu-id="67dc5-120">Client User: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="67dc5-121">説明</span><span class="sxs-lookup"><span data-stu-id="67dc5-121">Explanation</span></span>  
 <span data-ttu-id="67dc5-122">アプリケーション ユーザーには、グループ アプリケーションのマッピングを作成または制御するのに十分な特権がありません。</span><span class="sxs-lookup"><span data-stu-id="67dc5-122">An Application User does not have sufficient privileges to create or control mappings for Group applications.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="67dc5-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="67dc5-123">User Action</span></span>  
 <span data-ttu-id="67dc5-124">このアクティビティはアプリケーション管理者が実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67dc5-124">This activity must be performed by an Application Administrator.</span></span>
---
title: シングル サインオン:イベント 10557 |Microsoft Docs
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
ms.openlocfilehash: f5cd5be8005a1ce13c1ad5f13c580e6e72353b9b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398837"
---
# <a name="single-sign-on-event-10557"></a><span data-ttu-id="c82e6-102">シングル サインオン:イベント 10557</span><span class="sxs-lookup"><span data-stu-id="c82e6-102">Single Sign-On: Event 10557</span></span>
## <a name="details"></a><span data-ttu-id="c82e6-103">詳細</span><span class="sxs-lookup"><span data-stu-id="c82e6-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                          |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="c82e6-104">製品名</span><span class="sxs-lookup"><span data-stu-id="c82e6-104">Product Name</span></span>   |                                                                                        <span data-ttu-id="c82e6-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="c82e6-105">Enterprise Single Sign-On</span></span>                                                                                         |
| <span data-ttu-id="c82e6-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c82e6-106">Product Version</span></span> |                                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                        |
|    <span data-ttu-id="c82e6-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c82e6-107">Event ID</span></span>     |                                                                                                  <span data-ttu-id="c82e6-108">10557</span><span class="sxs-lookup"><span data-stu-id="c82e6-108">10557</span></span>                                                                                                   |
|  <span data-ttu-id="c82e6-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c82e6-109">Event Source</span></span>   |                                                                                                  <span data-ttu-id="c82e6-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c82e6-110">ENTSSO</span></span>                                                                                                  |
|    <span data-ttu-id="c82e6-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c82e6-111">Component</span></span>    |                                                                                                   <span data-ttu-id="c82e6-112">なし</span><span class="sxs-lookup"><span data-stu-id="c82e6-112">N/A</span></span>                                                                                                    |
|  <span data-ttu-id="c82e6-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c82e6-113">Symbolic Name</span></span>  |                                                                                   <span data-ttu-id="c82e6-114">SSO_WARN_USER_NOT_ALLOWED_FOR_GROUPS</span><span class="sxs-lookup"><span data-stu-id="c82e6-114">SSO_WARN_USER_NOT_ALLOWED_FOR_GROUPS</span></span>                                                                                   |
|  <span data-ttu-id="c82e6-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c82e6-115">Message Text</span></span>   | <span data-ttu-id="c82e6-116">アプリケーションのユーザーがグループ applications.%r のマッピングを制御する許可されていません</span><span class="sxs-lookup"><span data-stu-id="c82e6-116">Application Users are not allowed to control mappings for Group applications.%r</span></span><br /><br /> <span data-ttu-id="c82e6-117">ドメイン名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="c82e6-117">Domain Name: %1%r</span></span><br /><br /> <span data-ttu-id="c82e6-118">ユーザー名: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="c82e6-118">User Name: %2%r</span></span><br /><br /> <span data-ttu-id="c82e6-119">アプリケーション名: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="c82e6-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="c82e6-120">クライアント ユーザー: %4</span><span class="sxs-lookup"><span data-stu-id="c82e6-120">Client User: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="c82e6-121">説明</span><span class="sxs-lookup"><span data-stu-id="c82e6-121">Explanation</span></span>  
 <span data-ttu-id="c82e6-122">ユーザーがアプリケーションには、作成またはグループ アプリケーションに対するマッピングを制御するための十分な特権がありません。</span><span class="sxs-lookup"><span data-stu-id="c82e6-122">An Application User does not have sufficient privileges to create or control mappings for Group applications.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c82e6-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c82e6-123">User Action</span></span>  
 <span data-ttu-id="c82e6-124">このアクティビティは、アプリケーション管理者によって実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c82e6-124">This activity must be performed by an Application Administrator.</span></span>
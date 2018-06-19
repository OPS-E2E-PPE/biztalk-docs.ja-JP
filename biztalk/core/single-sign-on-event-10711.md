---
title: 'シングル サインオン: イベント 10711 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 40722fe1-4be9-40d3-b5c5-a740a4b59f45
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6c6bb3f85d45edd971a38b7e7fa4c1df3efb3cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271650"
---
# <a name="single-sign-on-event-10711"></a><span data-ttu-id="78159-102">シングル サインオン: イベント 10711</span><span class="sxs-lookup"><span data-stu-id="78159-102">Single Sign-On: Event 10711</span></span>
## <a name="details"></a><span data-ttu-id="78159-103">詳細</span><span class="sxs-lookup"><span data-stu-id="78159-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="78159-104">製品名</span><span class="sxs-lookup"><span data-stu-id="78159-104">Product Name</span></span>|<span data-ttu-id="78159-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="78159-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="78159-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="78159-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="78159-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="78159-107">Event ID</span></span>|<span data-ttu-id="78159-108">10711</span><span class="sxs-lookup"><span data-stu-id="78159-108">10711</span></span>|  
|<span data-ttu-id="78159-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="78159-109">Event Source</span></span>|<span data-ttu-id="78159-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="78159-110">ENTSSO</span></span>|  
|<span data-ttu-id="78159-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="78159-111">Component</span></span>|<span data-ttu-id="78159-112">N\A</span><span class="sxs-lookup"><span data-stu-id="78159-112">N\A</span></span>|  
|<span data-ttu-id="78159-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="78159-113">Symbolic Name</span></span>|<span data-ttu-id="78159-114">SSO_WARN_PS_MISSING_INITIAL_CREDS</span><span class="sxs-lookup"><span data-stu-id="78159-114">SSO_WARN_PS_MISSING_INITIAL_CREDS</span></span>|  
|<span data-ttu-id="78159-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="78159-115">Message Text</span></span>|<span data-ttu-id="78159-116">外部パスワードが変更されています。</span><span class="sxs-lookup"><span data-stu-id="78159-116">External password change.</span></span> <span data-ttu-id="78159-117">このマッピングで不足する外部資格情報フィールドの一部は既定値に設定されています。%r</span><span class="sxs-lookup"><span data-stu-id="78159-117">Some missing external credential fields for this mapping have been set to default values.%r</span></span><br /><br /> <span data-ttu-id="78159-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="78159-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="78159-119">アダプター: %2 %r</span><span class="sxs-lookup"><span data-stu-id="78159-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="78159-120">アプリケーション名: %3 %r</span><span class="sxs-lookup"><span data-stu-id="78159-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="78159-121">外部アカウント: %4</span><span class="sxs-lookup"><span data-stu-id="78159-121">External Account: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="78159-122">説明</span><span class="sxs-lookup"><span data-stu-id="78159-122">Explanation</span></span>  
 <span data-ttu-id="78159-123">この警告イベントは、外部パスワード変更が受信されたが、資格情報がないことを示します。</span><span class="sxs-lookup"><span data-stu-id="78159-123">This Warning event indicates that an external password change was received with missing credentials.</span></span> <span data-ttu-id="78159-124">これらのフィールドには、既定値が使用されていました。</span><span class="sxs-lookup"><span data-stu-id="78159-124">Default values were used in those fields.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="78159-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="78159-125">User Action</span></span>  
 <span data-ttu-id="78159-126">この警告を解決するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="78159-126">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="78159-127">必要に応じて、資格情報が一致するように設定します。</span><span class="sxs-lookup"><span data-stu-id="78159-127">If necessary, set the credentials to match.</span></span>  
  
 <span data-ttu-id="78159-128">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="78159-128">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="78159-129">SSO 関連アプリケーション</span><span class="sxs-lookup"><span data-stu-id="78159-129">SSO Affiliate Applications</span></span>](../core/sso-affiliate-applications.md)  
  
-   [<span data-ttu-id="78159-130">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="78159-130">Password Synchronization</span></span>](../core/password-synchronization2.md)
---
title: 'シングル サインオン: イベント 11057 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1e165e24-fe43-4899-ab6e-1437f639f534
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ca69661d1421433c44472e0572c5d4d4bf76a13
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278090"
---
# <a name="single-sign-on-event-11057"></a><span data-ttu-id="34f73-102">シングル サインオン: イベント 11057</span><span class="sxs-lookup"><span data-stu-id="34f73-102">Single Sign-On: Event 11057</span></span>
## <a name="details"></a><span data-ttu-id="34f73-103">詳細</span><span class="sxs-lookup"><span data-stu-id="34f73-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="34f73-104">製品名</span><span class="sxs-lookup"><span data-stu-id="34f73-104">Product Name</span></span>|<span data-ttu-id="34f73-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="34f73-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="34f73-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="34f73-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="34f73-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="34f73-107">Event ID</span></span>|<span data-ttu-id="34f73-108">11057</span><span class="sxs-lookup"><span data-stu-id="34f73-108">11057</span></span>|  
|<span data-ttu-id="34f73-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="34f73-109">Event Source</span></span>|<span data-ttu-id="34f73-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="34f73-110">ENTSSO</span></span>|  
|<span data-ttu-id="34f73-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="34f73-111">Component</span></span>|<span data-ttu-id="34f73-112">なし</span><span class="sxs-lookup"><span data-stu-id="34f73-112">N/A</span></span>|  
|<span data-ttu-id="34f73-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="34f73-113">Symbolic Name</span></span>|<span data-ttu-id="34f73-114">SSO_WARN_PS_DIRECT_MISSING_INITIAL_CREDS</span><span class="sxs-lookup"><span data-stu-id="34f73-114">SSO_WARN_PS_DIRECT_MISSING_INITIAL_CREDS</span></span>|  
|<span data-ttu-id="34f73-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="34f73-115">Message Text</span></span>|<span data-ttu-id="34f73-116">直接パスワード変更。</span><span class="sxs-lookup"><span data-stu-id="34f73-116">Direct password change.</span></span> <span data-ttu-id="34f73-117">このマッピングで不足する外部資格情報フィールドの一部は既定値に設定されています。%r</span><span class="sxs-lookup"><span data-stu-id="34f73-117">Some missing external credential fields for this mapping have been set to default values.%r</span></span><br /><br /> <span data-ttu-id="34f73-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="34f73-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="34f73-119">アプリケーション名: %2 %r</span><span class="sxs-lookup"><span data-stu-id="34f73-119">Application Name: %2%r</span></span><br /><br /> <span data-ttu-id="34f73-120">Windows アカウント: %3 %r</span><span class="sxs-lookup"><span data-stu-id="34f73-120">Windows Account: %3%r</span></span><br /><br /> <span data-ttu-id="34f73-121">外部アカウント: %4</span><span class="sxs-lookup"><span data-stu-id="34f73-121">External Account: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="34f73-122">説明</span><span class="sxs-lookup"><span data-stu-id="34f73-122">Explanation</span></span>  
 <span data-ttu-id="34f73-123">直接パスワード同期を使用してパスワードを変更できますが、この機能は外部資格情報フィールドを 1 つだけサポートしています。</span><span class="sxs-lookup"><span data-stu-id="34f73-123">While it is possible to change passwords using Direct Password Sync, this feature only supports one external credential field.</span></span> <span data-ttu-id="34f73-124">この場合、ENTSSO システムで複数の外部資格情報フィールドが検出されたため、これらのフィールドは既定 (空白) 値に設定されました。</span><span class="sxs-lookup"><span data-stu-id="34f73-124">In this case the ENTSSO System has encountered more than one external credential field, and has set those fields to default (blank) values.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="34f73-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="34f73-125">User Action</span></span>  
 <span data-ttu-id="34f73-126">ユーザーの操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="34f73-126">No user action is necessary.</span></span>
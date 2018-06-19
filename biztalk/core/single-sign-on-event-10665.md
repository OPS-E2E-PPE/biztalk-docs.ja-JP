---
title: 'シングル サインオン: イベント 10665 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d0de9d0-9b46-4f3a-b796-1ce3de01cf4c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a7d4d5c4140448914ff77b09a692cc3a2136dfc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271154"
---
# <a name="single-sign-on-event-10665"></a><span data-ttu-id="4c462-102">シングル サインオン: イベント 10665</span><span class="sxs-lookup"><span data-stu-id="4c462-102">Single Sign-On: Event 10665</span></span>
## <a name="details"></a><span data-ttu-id="4c462-103">詳細</span><span class="sxs-lookup"><span data-stu-id="4c462-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4c462-104">製品名</span><span class="sxs-lookup"><span data-stu-id="4c462-104">Product Name</span></span>|<span data-ttu-id="4c462-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="4c462-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="4c462-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="4c462-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="4c462-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4c462-107">Event ID</span></span>|<span data-ttu-id="4c462-108">10665</span><span class="sxs-lookup"><span data-stu-id="4c462-108">10665</span></span>|  
|<span data-ttu-id="4c462-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="4c462-109">Event Source</span></span>|<span data-ttu-id="4c462-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="4c462-110">ENTSSO</span></span>|  
|<span data-ttu-id="4c462-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="4c462-111">Component</span></span>|<span data-ttu-id="4c462-112">N\A</span><span class="sxs-lookup"><span data-stu-id="4c462-112">N\A</span></span>|  
|<span data-ttu-id="4c462-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="4c462-113">Symbolic Name</span></span>|<span data-ttu-id="4c462-114">SSO_WARN_NO_PROPERTIES</span><span class="sxs-lookup"><span data-stu-id="4c462-114">SSO_WARN_NO_PROPERTIES</span></span>|  
|<span data-ttu-id="4c462-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="4c462-115">Message Text</span></span>|<span data-ttu-id="4c462-116">パスワード同期アダプターのプロパティを読み取り中のエラー。</span><span class="sxs-lookup"><span data-stu-id="4c462-116">Error reading password sync adapter properties.</span></span> <span data-ttu-id="4c462-117">既定値を使用しています。%r</span><span class="sxs-lookup"><span data-stu-id="4c462-117">Using defaults.%r</span></span><br /><br /> <span data-ttu-id="4c462-118">アダプター: %1 %r</span><span class="sxs-lookup"><span data-stu-id="4c462-118">Adapter: %1%r</span></span><br /><br /> <span data-ttu-id="4c462-119">エラー コード: %2</span><span class="sxs-lookup"><span data-stu-id="4c462-119">Error Code: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4c462-120">説明</span><span class="sxs-lookup"><span data-stu-id="4c462-120">Explanation</span></span>  
 <span data-ttu-id="4c462-121">この警告イベントは、既定のパスワード同期アダプターのプロパティの読み取り中にエラーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="4c462-121">This Warning event indicates that there was an error reading the default password sync adapter properties.</span></span> <span data-ttu-id="4c462-122">各パスワード同期アダプターには、構成プロパティが関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="4c462-122">Each password sync adapter has configuration properties associated with it.</span></span> <span data-ttu-id="4c462-123">これらのプロパティは SSO 構成ストアに格納されており、パスワード同期アダプターが作成されるときに、SSO コマンド ライン ツールまたは SSO 管理 MMC によって作成されます。</span><span class="sxs-lookup"><span data-stu-id="4c462-123">These properties are stored in the SSO config store and are created by the SSO command line tools or the SSO Admin MMC when the password sync adapter is created.</span></span>  <span data-ttu-id="4c462-124">パスワード同期アダプターが他の方法で作成された場合、プロパティが不足している可能性があり、このエラーが発行される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4c462-124">There can be missing properties if the password sync adapter was created by any other means, then this error can be issued.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4c462-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="4c462-125">User Action</span></span>  
 <span data-ttu-id="4c462-126">この警告を解消するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="4c462-126">To resolve this warning, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="4c462-127">パスワード同期アダプターのプロパティを確認します。</span><span class="sxs-lookup"><span data-stu-id="4c462-127">Verify password sync adapter properties.</span></span>  
  
-   <span data-ttu-id="4c462-128">パスワード同期アダプターを再作成します。</span><span class="sxs-lookup"><span data-stu-id="4c462-128">Recreate the password sync adapter</span></span>  
  
## <a name="more-info"></a><span data-ttu-id="4c462-129">詳細</span><span class="sxs-lookup"><span data-stu-id="4c462-129">More info</span></span>
  
-   <span data-ttu-id="4c462-130">**パスワード同期アダプターのプロパティ: オプション**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="4c462-130">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
  
-   [<span data-ttu-id="4c462-131">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="4c462-131">Password Synchronization</span></span>](../core/password-synchronization2.md)
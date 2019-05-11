---
title: シングル サインオン:イベント 10665 |Microsoft Docs
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
ms.openlocfilehash: 47cd0f957ba835df7f7463a8ee9c33f7b4503eb6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397556"
---
# <a name="single-sign-on-event-10665"></a><span data-ttu-id="63823-102">シングル サインオン:イベント 10665</span><span class="sxs-lookup"><span data-stu-id="63823-102">Single Sign-On: Event 10665</span></span>
## <a name="details"></a><span data-ttu-id="63823-103">詳細</span><span class="sxs-lookup"><span data-stu-id="63823-103">Details</span></span>  

|                 |                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="63823-104">製品名</span><span class="sxs-lookup"><span data-stu-id="63823-104">Product Name</span></span>   |                                               <span data-ttu-id="63823-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="63823-105">Enterprise Single Sign-On</span></span>                                                |
| <span data-ttu-id="63823-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="63823-106">Product Version</span></span> |                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                               |
|    <span data-ttu-id="63823-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="63823-107">Event ID</span></span>     |                                                         <span data-ttu-id="63823-108">10665</span><span class="sxs-lookup"><span data-stu-id="63823-108">10665</span></span>                                                          |
|  <span data-ttu-id="63823-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="63823-109">Event Source</span></span>   |                                                         <span data-ttu-id="63823-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="63823-110">ENTSSO</span></span>                                                         |
|    <span data-ttu-id="63823-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="63823-111">Component</span></span>    |                                                          <span data-ttu-id="63823-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="63823-112">N\A</span></span>                                                           |
|  <span data-ttu-id="63823-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="63823-113">Symbolic Name</span></span>  |                                                 <span data-ttu-id="63823-114">SSO_WARN_NO_PROPERTIES</span><span class="sxs-lookup"><span data-stu-id="63823-114">SSO_WARN_NO_PROPERTIES</span></span>                                                 |
|  <span data-ttu-id="63823-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="63823-115">Message Text</span></span>   | <span data-ttu-id="63823-116">パスワード同期アダプターのプロパティの読み取りエラー。</span><span class="sxs-lookup"><span data-stu-id="63823-116">Error reading password sync adapter properties.</span></span> <span data-ttu-id="63823-117">Defaults.%r を使用します。</span><span class="sxs-lookup"><span data-stu-id="63823-117">Using defaults.%r</span></span><br /><br /> <span data-ttu-id="63823-118">アダプター: % 1 %r</span><span class="sxs-lookup"><span data-stu-id="63823-118">Adapter: %1%r</span></span><br /><br /> <span data-ttu-id="63823-119">エラー コード: %2</span><span class="sxs-lookup"><span data-stu-id="63823-119">Error Code: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="63823-120">説明</span><span class="sxs-lookup"><span data-stu-id="63823-120">Explanation</span></span>  
 <span data-ttu-id="63823-121">この警告イベントは、既定のパスワード同期アダプターのプロパティを読み取り中にエラーがあったことを示します。</span><span class="sxs-lookup"><span data-stu-id="63823-121">This Warning event indicates that there was an error reading the default password sync adapter properties.</span></span> <span data-ttu-id="63823-122">各パスワード同期アダプターには、関連付けられている構成プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="63823-122">Each password sync adapter has configuration properties associated with it.</span></span> <span data-ttu-id="63823-123">これらのプロパティは、SSO 構成ストアに格納され、パスワード同期アダプターが作成されるときに、SSO コマンド ライン ツールまたは SSO 管理 MMC によって作成されます。</span><span class="sxs-lookup"><span data-stu-id="63823-123">These properties are stored in the SSO config store and are created by the SSO command line tools or the SSO Admin MMC when the password sync adapter is created.</span></span>  <span data-ttu-id="63823-124">あることができます不足しているプロパティ、パスワード同期アダプターは、他の方法で作成された場合、このエラーが発生することができます。</span><span class="sxs-lookup"><span data-stu-id="63823-124">There can be missing properties if the password sync adapter was created by any other means, then this error can be issued.</span></span>  

## <a name="user-action"></a><span data-ttu-id="63823-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="63823-125">User Action</span></span>  
 <span data-ttu-id="63823-126">この警告を解決するには、次の 1 つ以上の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="63823-126">To resolve this warning, do one or more of the following:</span></span>  

-   <span data-ttu-id="63823-127">パスワード同期アダプターのプロパティを確認します。</span><span class="sxs-lookup"><span data-stu-id="63823-127">Verify password sync adapter properties.</span></span>  

-   <span data-ttu-id="63823-128">パスワード同期アダプターを再作成します。</span><span class="sxs-lookup"><span data-stu-id="63823-128">Recreate the password sync adapter</span></span>  

## <a name="more-info"></a><span data-ttu-id="63823-129">詳細情報</span><span class="sxs-lookup"><span data-stu-id="63823-129">More info</span></span>

- <span data-ttu-id="63823-130">**パスワード同期アダプターのプロパティ:オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="63823-130">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>

- [<span data-ttu-id="63823-131">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="63823-131">Password Synchronization</span></span>](../core/password-synchronization2.md)

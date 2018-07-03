---
title: アドレスの検証にバインドからスキームを取得することはできません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b002084a-63ae-4685-8ce3-88cc6489e19e
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2032decfdf59ae175f3ee8fc686341c8a4061fc6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991339"
---
# <a name="cannot-obtain-scheme-from-binding-to-validate-address"></a><span data-ttu-id="0933a-102">アドレスを検証するためのスキームをバインドから取得できません</span><span class="sxs-lookup"><span data-stu-id="0933a-102">Cannot obtain scheme from binding to validate address</span></span>
## <a name="details"></a><span data-ttu-id="0933a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="0933a-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="0933a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="0933a-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="0933a-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="0933a-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="0933a-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0933a-106">Event ID</span></span>     |                                         <span data-ttu-id="0933a-107">0</span><span class="sxs-lookup"><span data-stu-id="0933a-107">0</span></span>                                          |
|  <span data-ttu-id="0933a-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="0933a-108">Event Source</span></span>   |                                         <span data-ttu-id="0933a-109">0</span><span class="sxs-lookup"><span data-stu-id="0933a-109">0</span></span>                                          |
|    <span data-ttu-id="0933a-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0933a-110">Component</span></span>    |                                         <span data-ttu-id="0933a-111">0</span><span class="sxs-lookup"><span data-stu-id="0933a-111">0</span></span>                                          |
|  <span data-ttu-id="0933a-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="0933a-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="0933a-113">0</span><span class="sxs-lookup"><span data-stu-id="0933a-113">0</span></span>                                          |
|  <span data-ttu-id="0933a-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="0933a-114">Message Text</span></span>   |               <span data-ttu-id="0933a-115">アドレスを検証するためのスキームをバインドから取得できません。</span><span class="sxs-lookup"><span data-stu-id="0933a-115">Cannot obtain scheme from binding to validate address.</span></span>               |
  
## <a name="explanation"></a><span data-ttu-id="0933a-116">説明</span><span class="sxs-lookup"><span data-stu-id="0933a-116">Explanation</span></span>  
 <span data-ttu-id="0933a-117">指定されているトランスポート バインド要素にスキームがありません。</span><span class="sxs-lookup"><span data-stu-id="0933a-117">The transport binding element that has been specified does not have a scheme.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0933a-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="0933a-118">User Action</span></span>  
 <span data-ttu-id="0933a-119">トランスポート バインディング要素に有効なスキームがあること、または有効なトランスポート バインディング要素が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0933a-119">Make sure that the transport binding element has a valid scheme, or that a valid transport binding element is selected.</span></span> <span data-ttu-id="0933a-120">カスタム バインドを使用する場合は、有効なトランスポート バインド要素が指定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0933a-120">If using a custom binding, make sure a valid transport binding element is specified.</span></span>  
  
 <span data-ttu-id="0933a-121">詳細については、の次のリソースを参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。</span><span class="sxs-lookup"><span data-stu-id="0933a-121">For additional information, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="0933a-122">WCF-Custom アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="0933a-122">Configuring the WCF-Custom Adapter</span></span>](../core/configuring-the-wcf-custom-adapter.md)
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
ms.openlocfilehash: 1d42116dff2ad72b4d076b7c6e5303f1d8636e9f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358069"
---
# <a name="cannot-obtain-scheme-from-binding-to-validate-address"></a><span data-ttu-id="30c76-102">アドレスを検証するためのスキームをバインドから取得できません</span><span class="sxs-lookup"><span data-stu-id="30c76-102">Cannot obtain scheme from binding to validate address</span></span>
## <a name="details"></a><span data-ttu-id="30c76-103">詳細</span><span class="sxs-lookup"><span data-stu-id="30c76-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="30c76-104">製品名</span><span class="sxs-lookup"><span data-stu-id="30c76-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="30c76-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="30c76-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="30c76-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="30c76-106">Event ID</span></span>     |                                         <span data-ttu-id="30c76-107">0</span><span class="sxs-lookup"><span data-stu-id="30c76-107">0</span></span>                                          |
|  <span data-ttu-id="30c76-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="30c76-108">Event Source</span></span>   |                                         <span data-ttu-id="30c76-109">0</span><span class="sxs-lookup"><span data-stu-id="30c76-109">0</span></span>                                          |
|    <span data-ttu-id="30c76-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="30c76-110">Component</span></span>    |                                         <span data-ttu-id="30c76-111">0</span><span class="sxs-lookup"><span data-stu-id="30c76-111">0</span></span>                                          |
|  <span data-ttu-id="30c76-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="30c76-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="30c76-113">0</span><span class="sxs-lookup"><span data-stu-id="30c76-113">0</span></span>                                          |
|  <span data-ttu-id="30c76-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="30c76-114">Message Text</span></span>   |               <span data-ttu-id="30c76-115">アドレスの検証にバインディングからスキームを取得できません。</span><span class="sxs-lookup"><span data-stu-id="30c76-115">Cannot obtain scheme from binding to validate address.</span></span>               |
  
## <a name="explanation"></a><span data-ttu-id="30c76-116">説明</span><span class="sxs-lookup"><span data-stu-id="30c76-116">Explanation</span></span>  
 <span data-ttu-id="30c76-117">指定されたトランスポート バインド要素のスキームではありません。</span><span class="sxs-lookup"><span data-stu-id="30c76-117">The transport binding element that has been specified does not have a scheme.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="30c76-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="30c76-118">User Action</span></span>  
 <span data-ttu-id="30c76-119">トランスポート バインド要素は、有効なスキームであるか、有効なトランスポート バインド要素が選択されているようにします。</span><span class="sxs-lookup"><span data-stu-id="30c76-119">Make sure that the transport binding element has a valid scheme, or that a valid transport binding element is selected.</span></span> <span data-ttu-id="30c76-120">カスタム バインドを使用する場合、有効なトランスポート バインド要素が指定されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="30c76-120">If using a custom binding, make sure a valid transport binding element is specified.</span></span>  
  
 <span data-ttu-id="30c76-121">詳細については、の次のリソースを参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。</span><span class="sxs-lookup"><span data-stu-id="30c76-121">For additional information, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="30c76-122">WCF-Custom アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="30c76-122">Configuring the WCF-Custom Adapter</span></span>](../core/configuring-the-wcf-custom-adapter.md)
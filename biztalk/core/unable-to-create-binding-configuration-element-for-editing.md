---
title: 編集対象のバインド構成要素を作成できません |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71853662-5a4a-417e-8160-c93dbcbea336
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98e58ec9966d0e0534d078fc5741f267bf02e735
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974339"
---
# <a name="unable-to-create-binding-configuration-element-for-editing"></a><span data-ttu-id="cc407-102">編集対象のバインド構成要素を作成できません</span><span class="sxs-lookup"><span data-stu-id="cc407-102">Unable to create binding configuration element for editing</span></span>
## <a name="details"></a><span data-ttu-id="cc407-103">詳細</span><span class="sxs-lookup"><span data-stu-id="cc407-103">Details</span></span>  
  
|                 |                                                                                                                                      |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="cc407-104">製品名</span><span class="sxs-lookup"><span data-stu-id="cc407-104">Product Name</span></span>   |                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                          |
| <span data-ttu-id="cc407-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="cc407-105">Product Version</span></span> |                                      [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                      |
|    <span data-ttu-id="cc407-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="cc407-106">Event ID</span></span>     |                                                                  <span data-ttu-id="cc407-107">0</span><span class="sxs-lookup"><span data-stu-id="cc407-107">0</span></span>                                                                   |
|  <span data-ttu-id="cc407-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="cc407-108">Event Source</span></span>   |                                                                  <span data-ttu-id="cc407-109">0</span><span class="sxs-lookup"><span data-stu-id="cc407-109">0</span></span>                                                                   |
|    <span data-ttu-id="cc407-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="cc407-110">Component</span></span>    |                                                                  <span data-ttu-id="cc407-111">0</span><span class="sxs-lookup"><span data-stu-id="cc407-111">0</span></span>                                                                   |
|  <span data-ttu-id="cc407-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="cc407-112">Symbolic Name</span></span>  |                                                                  <span data-ttu-id="cc407-113">0</span><span class="sxs-lookup"><span data-stu-id="cc407-113">0</span></span>                                                                   |
|  <span data-ttu-id="cc407-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="cc407-114">Message Text</span></span>   | <span data-ttu-id="cc407-115">編集対象のバインド構成要素を作成できません。</span><span class="sxs-lookup"><span data-stu-id="cc407-115">Unable to create binding configuration element for editing.</span></span> <span data-ttu-id="cc407-116">BindingType プロパティおよび BindingConfiguration プロパティの値を確認してください。</span><span class="sxs-lookup"><span data-stu-id="cc407-116">Check the values of the BindingType and BindingConfiguration properties.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="cc407-117">説明</span><span class="sxs-lookup"><span data-stu-id="cc407-117">Explanation</span></span>  
 <span data-ttu-id="cc407-118">ユーザー インターフェイスに表示するバインディング要素を読み込むときに、エラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="cc407-118">There was an error loading a binding element for display in the user interface.</span></span> <span data-ttu-id="cc407-119">このエラーはカスタム バインディングの場合によく発生します。</span><span class="sxs-lookup"><span data-stu-id="cc407-119">This error often occurs with custom binding.</span></span> <span data-ttu-id="cc407-120">構成ファイルにバインディング要素がないために、バインディングのドロップダウン リストで使用できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cc407-120">The binding element is probably missing in the configuration file and is therefore not available on the drop-down list for binding.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cc407-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="cc407-121">User Action</span></span>  
 <span data-ttu-id="cc407-122">値を確認、 **BindingType**と**BindingConfiguration**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="cc407-122">Check the values of the **BindingType** and **BindingConfiguration** properties.</span></span>  
  
 <span data-ttu-id="cc407-123">バインディング構成要素の作成の詳細については、次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc407-123">For further information on creating binding configuration elements, see the following resource:</span></span>  
  
-   [<span data-ttu-id="cc407-124">WCF-NetMsmq アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="cc407-124">Configuring the WCF-NetMsmq Adapter</span></span>](../core/configuring-the-wcf-netmsmq-adapter.md)
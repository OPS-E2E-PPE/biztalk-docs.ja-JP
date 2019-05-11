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
ms.openlocfilehash: c508f4839937315c64734f650fe84e87c60c0dcb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292875"
---
# <a name="unable-to-create-binding-configuration-element-for-editing"></a><span data-ttu-id="a46c0-102">編集対象のバインド構成要素を作成できません</span><span class="sxs-lookup"><span data-stu-id="a46c0-102">Unable to create binding configuration element for editing</span></span>
## <a name="details"></a><span data-ttu-id="a46c0-103">詳細</span><span class="sxs-lookup"><span data-stu-id="a46c0-103">Details</span></span>  
  
|                 |                                                                                                                                      |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="a46c0-104">製品名</span><span class="sxs-lookup"><span data-stu-id="a46c0-104">Product Name</span></span>   |                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                          |
| <span data-ttu-id="a46c0-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="a46c0-105">Product Version</span></span> |                                      [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                      |
|    <span data-ttu-id="a46c0-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="a46c0-106">Event ID</span></span>     |                                                                  <span data-ttu-id="a46c0-107">0</span><span class="sxs-lookup"><span data-stu-id="a46c0-107">0</span></span>                                                                   |
|  <span data-ttu-id="a46c0-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="a46c0-108">Event Source</span></span>   |                                                                  <span data-ttu-id="a46c0-109">0</span><span class="sxs-lookup"><span data-stu-id="a46c0-109">0</span></span>                                                                   |
|    <span data-ttu-id="a46c0-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a46c0-110">Component</span></span>    |                                                                  <span data-ttu-id="a46c0-111">0</span><span class="sxs-lookup"><span data-stu-id="a46c0-111">0</span></span>                                                                   |
|  <span data-ttu-id="a46c0-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="a46c0-112">Symbolic Name</span></span>  |                                                                  <span data-ttu-id="a46c0-113">0</span><span class="sxs-lookup"><span data-stu-id="a46c0-113">0</span></span>                                                                   |
|  <span data-ttu-id="a46c0-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="a46c0-114">Message Text</span></span>   | <span data-ttu-id="a46c0-115">編集対象のバインド構成要素を作成できません。</span><span class="sxs-lookup"><span data-stu-id="a46c0-115">Unable to create binding configuration element for editing.</span></span> <span data-ttu-id="a46c0-116">BindingType プロパティおよび BindingConfiguration プロパティの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="a46c0-116">Check the values of the BindingType and BindingConfiguration properties.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="a46c0-117">説明</span><span class="sxs-lookup"><span data-stu-id="a46c0-117">Explanation</span></span>  
 <span data-ttu-id="a46c0-118">ユーザー インターフェイスに表示するバインド要素を読み込み中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="a46c0-118">There was an error loading a binding element for display in the user interface.</span></span> <span data-ttu-id="a46c0-119">このエラーは、多くの場合、カスタム バインドで発生します。</span><span class="sxs-lookup"><span data-stu-id="a46c0-119">This error often occurs with custom binding.</span></span> <span data-ttu-id="a46c0-120">バインド要素は、構成ファイルが不足している可能性がありますし、したがってはバインディングのドロップダウン リストで使用できません。</span><span class="sxs-lookup"><span data-stu-id="a46c0-120">The binding element is probably missing in the configuration file and is therefore not available on the drop-down list for binding.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a46c0-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="a46c0-121">User Action</span></span>  
 <span data-ttu-id="a46c0-122">値を確認、 **BindingType**と**BindingConfiguration**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="a46c0-122">Check the values of the **BindingType** and **BindingConfiguration** properties.</span></span>  
  
 <span data-ttu-id="a46c0-123">バインディング構成要素を作成する方法の詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a46c0-123">For further information on creating binding configuration elements, see the following resource:</span></span>  
  
-   [<span data-ttu-id="a46c0-124">WCF-NetMsmq アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="a46c0-124">Configuring the WCF-NetMsmq Adapter</span></span>](../core/configuring-the-wcf-netmsmq-adapter.md)
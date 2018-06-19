---
title: 編集するためのバインディング構成要素を作成できません |。Microsoft ドキュメント
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
ms.openlocfilehash: a5c4387e0cb9287ecc4d491291fdfd1fa6b79ab9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286426"
---
# <a name="unable-to-create-binding-configuration-element-for-editing"></a><span data-ttu-id="2ae48-102">編集対象のバインド構成要素を作成できません</span><span class="sxs-lookup"><span data-stu-id="2ae48-102">Unable to create binding configuration element for editing</span></span>
## <a name="details"></a><span data-ttu-id="2ae48-103">詳細</span><span class="sxs-lookup"><span data-stu-id="2ae48-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2ae48-104">製品名</span><span class="sxs-lookup"><span data-stu-id="2ae48-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="2ae48-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="2ae48-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="2ae48-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="2ae48-106">Event ID</span></span>|<span data-ttu-id="2ae48-107">0</span><span class="sxs-lookup"><span data-stu-id="2ae48-107">0</span></span>|  
|<span data-ttu-id="2ae48-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="2ae48-108">Event Source</span></span>|<span data-ttu-id="2ae48-109">0</span><span class="sxs-lookup"><span data-stu-id="2ae48-109">0</span></span>|  
|<span data-ttu-id="2ae48-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2ae48-110">Component</span></span>|<span data-ttu-id="2ae48-111">0</span><span class="sxs-lookup"><span data-stu-id="2ae48-111">0</span></span>|  
|<span data-ttu-id="2ae48-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="2ae48-112">Symbolic Name</span></span>|<span data-ttu-id="2ae48-113">0</span><span class="sxs-lookup"><span data-stu-id="2ae48-113">0</span></span>|  
|<span data-ttu-id="2ae48-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="2ae48-114">Message Text</span></span>|<span data-ttu-id="2ae48-115">編集対象のバインド構成要素を作成できません。</span><span class="sxs-lookup"><span data-stu-id="2ae48-115">Unable to create binding configuration element for editing.</span></span> <span data-ttu-id="2ae48-116">BindingType プロパティおよび BindingConfiguration プロパティの値を確認してください。</span><span class="sxs-lookup"><span data-stu-id="2ae48-116">Check the values of the BindingType and BindingConfiguration properties.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2ae48-117">説明</span><span class="sxs-lookup"><span data-stu-id="2ae48-117">Explanation</span></span>  
 <span data-ttu-id="2ae48-118">ユーザー インターフェイスに表示するバインディング要素を読み込むときに、エラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="2ae48-118">There was an error loading a binding element for display in the user interface.</span></span> <span data-ttu-id="2ae48-119">このエラーはカスタム バインディングの場合によく発生します。</span><span class="sxs-lookup"><span data-stu-id="2ae48-119">This error often occurs with custom binding.</span></span> <span data-ttu-id="2ae48-120">構成ファイルにバインディング要素がないために、バインディングのドロップダウン リストで使用できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2ae48-120">The binding element is probably missing in the configuration file and is therefore not available on the drop-down list for binding.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2ae48-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="2ae48-121">User Action</span></span>  
 <span data-ttu-id="2ae48-122">値を確認、 **BindingType**と**BindingConfiguration**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="2ae48-122">Check the values of the **BindingType** and **BindingConfiguration** properties.</span></span>  
  
 <span data-ttu-id="2ae48-123">バインディング構成要素の作成の詳細については、次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ae48-123">For further information on creating binding configuration elements, see the following resource:</span></span>  
  
-   [<span data-ttu-id="2ae48-124">Wcf-netmsmq アダプタを構成します。</span><span class="sxs-lookup"><span data-stu-id="2ae48-124">Configuring the WCF-NetMsmq Adapter</span></span>](../core/configuring-the-wcf-netmsmq-adapter.md)
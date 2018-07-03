---
title: パブリック オーケストレーションなしに受信ポートをこの BizTalk アセンブリがある |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb901d49-ce3c-4bc6-806a-eb5964d32bb4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c062f5e23972ed841c4c9d614ad58967a07a4fe2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978217"
---
# <a name="there-are-no-orchestrations-with-public-receive-ports-in-this-biztalk-assembly"></a><span data-ttu-id="d33fd-102">この BizTalk アセンブリには、パブリック受信ポートを保持するオーケストレーションがありません</span><span class="sxs-lookup"><span data-stu-id="d33fd-102">There are no orchestrations with public receive ports in this BizTalk assembly</span></span>
## <a name="details"></a><span data-ttu-id="d33fd-103">詳細</span><span class="sxs-lookup"><span data-stu-id="d33fd-103">Details</span></span>  
  
|                 |                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="d33fd-104">製品名</span><span class="sxs-lookup"><span data-stu-id="d33fd-104">Product Name</span></span>   |                                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                               |
| <span data-ttu-id="d33fd-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d33fd-105">Product Version</span></span> |                                                          [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                           |
|    <span data-ttu-id="d33fd-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d33fd-106">Event ID</span></span>     |                                                                                       <span data-ttu-id="d33fd-107">0</span><span class="sxs-lookup"><span data-stu-id="d33fd-107">0</span></span>                                                                                       |
|  <span data-ttu-id="d33fd-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d33fd-108">Event Source</span></span>   |                                                                                       <span data-ttu-id="d33fd-109">0</span><span class="sxs-lookup"><span data-stu-id="d33fd-109">0</span></span>                                                                                       |
|    <span data-ttu-id="d33fd-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d33fd-110">Component</span></span>    |                                                                                       <span data-ttu-id="d33fd-111">0</span><span class="sxs-lookup"><span data-stu-id="d33fd-111">0</span></span>                                                                                       |
|  <span data-ttu-id="d33fd-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d33fd-112">Symbolic Name</span></span>  |                                                                                       <span data-ttu-id="d33fd-113">0</span><span class="sxs-lookup"><span data-stu-id="d33fd-113">0</span></span>                                                                                       |
|  <span data-ttu-id="d33fd-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d33fd-114">Message Text</span></span>   | <span data-ttu-id="d33fd-115">この BizTalk アセンブリには、パブリック受信ポートを保持するオーケストレーションがありません。</span><span class="sxs-lookup"><span data-stu-id="d33fd-115">There are no orchestrations with public receive ports in this BizTalk assembly.</span></span> <span data-ttu-id="d33fd-116">[戻る] をクリックして、パブリック受信ポートを保持するオーケストレーションを含む BizTalk アセンブリを指定してください。</span><span class="sxs-lookup"><span data-stu-id="d33fd-116">Click back and specify a BizTalk assembly containing orchestrations with public receive ports</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="d33fd-117">説明</span><span class="sxs-lookup"><span data-stu-id="d33fd-117">Explanation</span></span>  
 <span data-ttu-id="d33fd-118">このエラーは、選択したオーケストレーションにパブリック ポートがないことを示します。</span><span class="sxs-lookup"><span data-stu-id="d33fd-118">This error indicates the orchestration selected does not have a public port.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d33fd-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d33fd-119">User Action</span></span>  
 <span data-ttu-id="d33fd-120">パブリック ポートを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d33fd-120">Use the following procedure to configure a public port.</span></span>  
  
#### <a name="to-configure-a-public-port"></a><span data-ttu-id="d33fd-121">パブリック ポートを構成するには</span><span class="sxs-lookup"><span data-stu-id="d33fd-121">To configure a public port</span></span>  
  
1.  <span data-ttu-id="d33fd-122">オーケストレーションを特定し、目的の受信ポートをパブリックにします。</span><span class="sxs-lookup"><span data-stu-id="d33fd-122">Locate the orchestration and make the desired receive port public.</span></span>  
  
    1.  <span data-ttu-id="d33fd-123">ポート構成ウィザードを開きます。</span><span class="sxs-lookup"><span data-stu-id="d33fd-123">Open the Port Configuration wizard.</span></span>  
  
    2.  <span data-ttu-id="d33fd-124">**ポートの種類を選択します。**、変更**アクセス制限**から**内部**(既定)**パブリック - 制限なし**します。</span><span class="sxs-lookup"><span data-stu-id="d33fd-124">In **Select a Port Type**, change **Access Restrictions** from **Internal** (default) to **Public-no limits**.</span></span>  
  
2.  <span data-ttu-id="d33fd-125">アセンブリを再コンパイルします。</span><span class="sxs-lookup"><span data-stu-id="d33fd-125">Recompile the assembly.</span></span>  
  
     <span data-ttu-id="d33fd-126">\- または -</span><span class="sxs-lookup"><span data-stu-id="d33fd-126">\- OR -</span></span>  
  
     <span data-ttu-id="d33fd-127">パブリック受信ポートがある BizTalk アセンブリを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="d33fd-127">Load a BizTalk assembly with public receive ports.</span></span>
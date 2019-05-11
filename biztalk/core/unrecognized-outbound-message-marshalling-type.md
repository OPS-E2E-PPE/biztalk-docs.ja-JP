---
title: 認識されないの送信メッセージをマーシャ リングの種類 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e675112b-12f3-47ff-95f7-ce1a05db120e
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46ce69344cc642836f4eb82af6eda84bf40798a6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396049"
---
# <a name="unrecognized-outbound-message-marshalling-type"></a><span data-ttu-id="1a622-102">認識されない送信メッセージの型をマーシャ リング</span><span class="sxs-lookup"><span data-stu-id="1a622-102">Unrecognized outbound message marshalling type</span></span>
## <a name="details"></a><span data-ttu-id="1a622-103">詳細</span><span class="sxs-lookup"><span data-stu-id="1a622-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="1a622-104">製品名</span><span class="sxs-lookup"><span data-stu-id="1a622-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="1a622-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="1a622-105">Product Version</span></span> |               [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]               |
|    <span data-ttu-id="1a622-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="1a622-106">Event ID</span></span>     |                                           <span data-ttu-id="1a622-107">0</span><span class="sxs-lookup"><span data-stu-id="1a622-107">0</span></span>                                            |
|  <span data-ttu-id="1a622-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="1a622-108">Event Source</span></span>   |                                           <span data-ttu-id="1a622-109">0</span><span class="sxs-lookup"><span data-stu-id="1a622-109">0</span></span>                                            |
|    <span data-ttu-id="1a622-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1a622-110">Component</span></span>    |                                           <span data-ttu-id="1a622-111">0</span><span class="sxs-lookup"><span data-stu-id="1a622-111">0</span></span>                                            |
|  <span data-ttu-id="1a622-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="1a622-112">Symbolic Name</span></span>  |                                           <span data-ttu-id="1a622-113">0</span><span class="sxs-lookup"><span data-stu-id="1a622-113">0</span></span>                                            |
|  <span data-ttu-id="1a622-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="1a622-114">Message Text</span></span>   | <span data-ttu-id="1a622-115">認識されない送信メッセージの型をマーシャ リングUseBodyElement または UseTemplate が必要です</span><span class="sxs-lookup"><span data-stu-id="1a622-115">Unrecognized outbound message marshalling type; expected UseBodyElement or UseTemplate</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="1a622-116">説明</span><span class="sxs-lookup"><span data-stu-id="1a622-116">Explanation</span></span>  
 <span data-ttu-id="1a622-117">WCF です。OutboundBodyLocation プロパティは、カスタム パイプライン コンポーネントまたはオーケストレーションの UseBodyElement または UseTemplate とは異なる値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="1a622-117">The WCF.OutboundBodyLocation property is set to a value different than UseBodyElement or UseTemplate, in a custom pipeline component or orchestration.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1a622-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="1a622-118">User Action</span></span>  
 <span data-ttu-id="1a622-119">WCF を設定します。有効な値に OutboundBodyLocation プロパティです。</span><span class="sxs-lookup"><span data-stu-id="1a622-119">Set the WCF.OutboundBodyLocation property to a valid value.</span></span> <span data-ttu-id="1a622-120">有効な値は"UseBodyElement"または"UseTemplate"これは、コードを変更します。</span><span class="sxs-lookup"><span data-stu-id="1a622-120">Valid values are "UseBodyElement" or "UseTemplate" This is a code change.</span></span>   
<span data-ttu-id="1a622-121">送信メッセージの詳細については、の次のリソースを参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。</span><span class="sxs-lookup"><span data-stu-id="1a622-121">For further information about outbound messaging, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="1a622-122">WCF アダプター コンテキスト プロパティによる動的送信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="1a622-122">Configuring Dynamic Send Ports Using WCF Adapters Context Properties</span></span>](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)  
  
-   [<span data-ttu-id="1a622-123">WCF アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="1a622-123">Configuring the WCF Adapters</span></span>](../core/configuring-the-wcf-adapters.md)
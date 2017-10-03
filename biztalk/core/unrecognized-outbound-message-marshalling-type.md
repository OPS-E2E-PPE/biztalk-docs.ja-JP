---
title: "送信メッセージの認識できない型をマーシャ リング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e675112b-12f3-47ff-95f7-ce1a05db120e
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3928bde0d81a4fe22b7c16af41c3a4b6d5c7121c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="unrecognized-outbound-message-marshalling-type"></a><span data-ttu-id="2d8b1-102">送信メッセージのマーシャリングの種類が認識されません</span><span class="sxs-lookup"><span data-stu-id="2d8b1-102">Unrecognized outbound message marshalling type</span></span>
## <a name="details"></a><span data-ttu-id="2d8b1-103">詳細</span><span class="sxs-lookup"><span data-stu-id="2d8b1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2d8b1-104">製品名</span><span class="sxs-lookup"><span data-stu-id="2d8b1-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="2d8b1-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="2d8b1-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="2d8b1-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="2d8b1-106">Event ID</span></span>|<span data-ttu-id="2d8b1-107">0</span><span class="sxs-lookup"><span data-stu-id="2d8b1-107">0</span></span>|  
|<span data-ttu-id="2d8b1-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="2d8b1-108">Event Source</span></span>|<span data-ttu-id="2d8b1-109">0</span><span class="sxs-lookup"><span data-stu-id="2d8b1-109">0</span></span>|  
|<span data-ttu-id="2d8b1-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2d8b1-110">Component</span></span>|<span data-ttu-id="2d8b1-111">0</span><span class="sxs-lookup"><span data-stu-id="2d8b1-111">0</span></span>|  
|<span data-ttu-id="2d8b1-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="2d8b1-112">Symbolic Name</span></span>|<span data-ttu-id="2d8b1-113">0</span><span class="sxs-lookup"><span data-stu-id="2d8b1-113">0</span></span>|  
|<span data-ttu-id="2d8b1-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="2d8b1-114">Message Text</span></span>|<span data-ttu-id="2d8b1-115">送信メッセージのマーシャリングの種類が認識されません。UseBodyElement または UseTemplate が必要です。</span><span class="sxs-lookup"><span data-stu-id="2d8b1-115">Unrecognized outbound message marshalling type; expected UseBodyElement or UseTemplate</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2d8b1-116">説明</span><span class="sxs-lookup"><span data-stu-id="2d8b1-116">Explanation</span></span>  
 <span data-ttu-id="2d8b1-117">WCF.OutboundBodyLocation プロパティが、カスタムのパイプライン コンポーネントまたはオーケストレーションの UseBodyElement または UseTemplate とは異なる値に設定されています。</span><span class="sxs-lookup"><span data-stu-id="2d8b1-117">The WCF.OutboundBodyLocation property is set to a value different than UseBodyElement or UseTemplate, in a custom pipeline component or orchestration.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2d8b1-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="2d8b1-118">User Action</span></span>  
 <span data-ttu-id="2d8b1-119">WCF.OutboundBodyLocation プロパティを有効な値に設定します。</span><span class="sxs-lookup"><span data-stu-id="2d8b1-119">Set the WCF.OutboundBodyLocation property to a valid value.</span></span> <span data-ttu-id="2d8b1-120">有効な値は "UseBodyElement" または "UseTemplate" です。これはコードの変更です。</span><span class="sxs-lookup"><span data-stu-id="2d8b1-120">Valid values are "UseBodyElement" or "UseTemplate" This is a code change.</span></span>   
<span data-ttu-id="2d8b1-121">送信メッセージの詳細については、次のリソースを参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。</span><span class="sxs-lookup"><span data-stu-id="2d8b1-121">For further information about outbound messaging, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="2d8b1-122">WCF アダプター コンテキスト プロパティを使用して動的送信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="2d8b1-122">Configuring Dynamic Send Ports Using WCF Adapters Context Properties</span></span>](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)  
  
-   [<span data-ttu-id="2d8b1-123">WCF アダプタの構成</span><span class="sxs-lookup"><span data-stu-id="2d8b1-123">Configuring the WCF Adapters</span></span>](../core/configuring-the-wcf-adapters.md)
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
ms.openlocfilehash: cda3e7bd3d20e39bb59c2c1fbe14dfc964fd541a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023432"
---
# <a name="unrecognized-outbound-message-marshalling-type"></a><span data-ttu-id="0e661-102">送信メッセージのマーシャリングの種類が認識されません</span><span class="sxs-lookup"><span data-stu-id="0e661-102">Unrecognized outbound message marshalling type</span></span>
## <a name="details"></a><span data-ttu-id="0e661-103">詳細</span><span class="sxs-lookup"><span data-stu-id="0e661-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="0e661-104">製品名</span><span class="sxs-lookup"><span data-stu-id="0e661-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="0e661-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="0e661-105">Product Version</span></span> |               [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]               |
|    <span data-ttu-id="0e661-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0e661-106">Event ID</span></span>     |                                           <span data-ttu-id="0e661-107">0</span><span class="sxs-lookup"><span data-stu-id="0e661-107">0</span></span>                                            |
|  <span data-ttu-id="0e661-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="0e661-108">Event Source</span></span>   |                                           <span data-ttu-id="0e661-109">0</span><span class="sxs-lookup"><span data-stu-id="0e661-109">0</span></span>                                            |
|    <span data-ttu-id="0e661-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0e661-110">Component</span></span>    |                                           <span data-ttu-id="0e661-111">0</span><span class="sxs-lookup"><span data-stu-id="0e661-111">0</span></span>                                            |
|  <span data-ttu-id="0e661-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="0e661-112">Symbolic Name</span></span>  |                                           <span data-ttu-id="0e661-113">0</span><span class="sxs-lookup"><span data-stu-id="0e661-113">0</span></span>                                            |
|  <span data-ttu-id="0e661-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="0e661-114">Message Text</span></span>   | <span data-ttu-id="0e661-115">送信メッセージのマーシャリングの種類が認識されません。UseBodyElement または UseTemplate が必要です。</span><span class="sxs-lookup"><span data-stu-id="0e661-115">Unrecognized outbound message marshalling type; expected UseBodyElement or UseTemplate</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="0e661-116">説明</span><span class="sxs-lookup"><span data-stu-id="0e661-116">Explanation</span></span>  
 <span data-ttu-id="0e661-117">WCF.OutboundBodyLocation プロパティが、カスタムのパイプライン コンポーネントまたはオーケストレーションの UseBodyElement または UseTemplate とは異なる値に設定されています。</span><span class="sxs-lookup"><span data-stu-id="0e661-117">The WCF.OutboundBodyLocation property is set to a value different than UseBodyElement or UseTemplate, in a custom pipeline component or orchestration.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0e661-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="0e661-118">User Action</span></span>  
 <span data-ttu-id="0e661-119">WCF.OutboundBodyLocation プロパティを有効な値に設定します。</span><span class="sxs-lookup"><span data-stu-id="0e661-119">Set the WCF.OutboundBodyLocation property to a valid value.</span></span> <span data-ttu-id="0e661-120">有効な値は "UseBodyElement" または "UseTemplate" です。これはコードの変更です。</span><span class="sxs-lookup"><span data-stu-id="0e661-120">Valid values are "UseBodyElement" or "UseTemplate" This is a code change.</span></span>   
<span data-ttu-id="0e661-121">送信メッセージの詳細については、の次のリソースを参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。</span><span class="sxs-lookup"><span data-stu-id="0e661-121">For further information about outbound messaging, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="0e661-122">WCF アダプター コンテキスト プロパティによる動的送信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="0e661-122">Configuring Dynamic Send Ports Using WCF Adapters Context Properties</span></span>](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)  
  
-   [<span data-ttu-id="0e661-123">WCF アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="0e661-123">Configuring the WCF Adapters</span></span>](../core/configuring-the-wcf-adapters.md)
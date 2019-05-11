---
title: BizTalk メッセージ本文の要素が指定されていない |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af5d63c0-af96-4e34-828f-d29638cdf46d
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90a5f39c6bdfd281ae96fe488ae71fa5c4032adc
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528302"
---
# <a name="biztalk-message-body-element-not-specified"></a><span data-ttu-id="7539e-102">BizTalk メッセージ本文要素が指定されていません</span><span class="sxs-lookup"><span data-stu-id="7539e-102">BizTalk message body element not specified</span></span>
## <a name="details"></a><span data-ttu-id="7539e-103">詳細</span><span class="sxs-lookup"><span data-stu-id="7539e-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="7539e-104">製品名</span><span class="sxs-lookup"><span data-stu-id="7539e-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="7539e-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="7539e-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="7539e-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7539e-106">Event ID</span></span>     |                                         <span data-ttu-id="7539e-107">0</span><span class="sxs-lookup"><span data-stu-id="7539e-107">0</span></span>                                          |
|  <span data-ttu-id="7539e-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="7539e-108">Event Source</span></span>   |                                         <span data-ttu-id="7539e-109">0</span><span class="sxs-lookup"><span data-stu-id="7539e-109">0</span></span>                                          |
|    <span data-ttu-id="7539e-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7539e-110">Component</span></span>    |                                         <span data-ttu-id="7539e-111">0</span><span class="sxs-lookup"><span data-stu-id="7539e-111">0</span></span>                                          |
|  <span data-ttu-id="7539e-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="7539e-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="7539e-113">0</span><span class="sxs-lookup"><span data-stu-id="7539e-113">0</span></span>                                          |
|  <span data-ttu-id="7539e-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="7539e-114">Message Text</span></span>   |                     <span data-ttu-id="7539e-115">BizTalk メッセージ本文要素が指定されていません</span><span class="sxs-lookup"><span data-stu-id="7539e-115">BizTalk message body element not specified</span></span>                     |
  
## <a name="explanation"></a><span data-ttu-id="7539e-116">説明</span><span class="sxs-lookup"><span data-stu-id="7539e-116">Explanation</span></span>  
 <span data-ttu-id="7539e-117">このエラーは、送信 WCF メッセージのテンプレート オプションの使用を示します。</span><span class="sxs-lookup"><span data-stu-id="7539e-117">This error indicates the use of the template option for the outbound WCF message.</span></span> <span data-ttu-id="7539e-118">ただし、テンプレート式には、BizTalk メッセージ本文の要素が含まれていません。</span><span class="sxs-lookup"><span data-stu-id="7539e-118">However, the template expression doesn’t contain the BizTalk message body element.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7539e-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="7539e-119">User Action</span></span>  
 <span data-ttu-id="7539e-120">テンプレート式に次の要素が含まれていることを確認: \< **bts メッセージの本文の xmlns ="<http://www.microsoft.com/schemas/bts2007>"encoding ="[xml&#124;base64&#124;16 進&#124;文字列]"/**\>します。</span><span class="sxs-lookup"><span data-stu-id="7539e-120">Ensure that the template expression contains the following element: \<**bts-msg-body xmlns="<http://www.microsoft.com/schemas/bts2007>" encoding="[xml&#124;base64&#124;hex&#124;string]"/**\>.</span></span>
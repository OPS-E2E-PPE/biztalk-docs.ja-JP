---
title: 無効なクライアント証明書の拇印 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f18fa0a2-b0d9-4190-aa96-12ab7007edd1
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3f349dbc2eb3ffd6a1bfa38c3231461d45a8ae7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381386"
---
# <a name="invalid-client-certificate-thumbprint"></a><span data-ttu-id="abf6f-102">クライアント証明書の拇印が無効です</span><span class="sxs-lookup"><span data-stu-id="abf6f-102">Invalid client certificate thumbprint</span></span>
## <a name="details"></a><span data-ttu-id="abf6f-103">詳細</span><span class="sxs-lookup"><span data-stu-id="abf6f-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="abf6f-104">製品名</span><span class="sxs-lookup"><span data-stu-id="abf6f-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="abf6f-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="abf6f-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="abf6f-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="abf6f-106">Event ID</span></span>     |                                         <span data-ttu-id="abf6f-107">0</span><span class="sxs-lookup"><span data-stu-id="abf6f-107">0</span></span>                                          |
|  <span data-ttu-id="abf6f-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="abf6f-108">Event Source</span></span>   |                                         <span data-ttu-id="abf6f-109">0</span><span class="sxs-lookup"><span data-stu-id="abf6f-109">0</span></span>                                          |
|    <span data-ttu-id="abf6f-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="abf6f-110">Component</span></span>    |                                         <span data-ttu-id="abf6f-111">0</span><span class="sxs-lookup"><span data-stu-id="abf6f-111">0</span></span>                                          |
|  <span data-ttu-id="abf6f-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="abf6f-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="abf6f-113">0</span><span class="sxs-lookup"><span data-stu-id="abf6f-113">0</span></span>                                          |
|  <span data-ttu-id="abf6f-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="abf6f-114">Message Text</span></span>   |       <span data-ttu-id="abf6f-115">無効なクライアント証明書の拇印。40 桁の 16 進数が必要です。</span><span class="sxs-lookup"><span data-stu-id="abf6f-115">Invalid client certificate thumbprint; expected 40 hexadecimal digits.</span></span>       |
  
## <a name="explanation"></a><span data-ttu-id="abf6f-116">説明</span><span class="sxs-lookup"><span data-stu-id="abf6f-116">Explanation</span></span>  
 <span data-ttu-id="abf6f-117">無効なクライアント証明書の拇印が指定されました。</span><span class="sxs-lookup"><span data-stu-id="abf6f-117">An invalid client certificate thumbprint was specified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="abf6f-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="abf6f-118">User Action</span></span>  
 <span data-ttu-id="abf6f-119">WCF 送信ポートを構成するコードでは、ユーザー インターフェイスのクライアント証明書のプロパティには 40 桁の 16 進数の値が期待しています。</span><span class="sxs-lookup"><span data-stu-id="abf6f-119">In the code configuring the WCF send port, the client certificate property of the user interface expects a hexadecimal 40-digit value.</span></span> <span data-ttu-id="abf6f-120">例:798A68E7A3E6F2CCC6929FC4AF2A15A9EED66E39</span><span class="sxs-lookup"><span data-stu-id="abf6f-120">Example: 798A68E7A3E6F2CCC6929FC4AF2A15A9EED66E39</span></span>  
  
 <span data-ttu-id="abf6f-121">証明書の詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abf6f-121">For additional information on certificates, see the following:</span></span>  
  
-   [<span data-ttu-id="abf6f-122">WCF アダプターの証明書のインストール</span><span class="sxs-lookup"><span data-stu-id="abf6f-122">Installing Certificates for the WCF Adapters</span></span>](../core/installing-certificates-for-the-wcf-adapters.md)
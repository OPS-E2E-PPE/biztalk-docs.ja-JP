---
title: 無効なサービス証明書の拇印 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 22e7d74e-40ec-4187-9246-bc8da2a9ce86
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5dcd37c3f3f2d56a9bdc2c576fee344a0eef7df4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005148"
---
# <a name="invalid-service-certificate-thumbprint"></a><span data-ttu-id="e3c45-102">サービス証明書の拇印が無効です</span><span class="sxs-lookup"><span data-stu-id="e3c45-102">Invalid service certificate thumbprint</span></span>
## <a name="details"></a><span data-ttu-id="e3c45-103">詳細</span><span class="sxs-lookup"><span data-stu-id="e3c45-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="e3c45-104">製品名</span><span class="sxs-lookup"><span data-stu-id="e3c45-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="e3c45-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="e3c45-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="e3c45-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e3c45-106">Event ID</span></span>     |                                         <span data-ttu-id="e3c45-107">0</span><span class="sxs-lookup"><span data-stu-id="e3c45-107">0</span></span>                                          |
|  <span data-ttu-id="e3c45-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="e3c45-108">Event Source</span></span>   |                                         <span data-ttu-id="e3c45-109">0</span><span class="sxs-lookup"><span data-stu-id="e3c45-109">0</span></span>                                          |
|    <span data-ttu-id="e3c45-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e3c45-110">Component</span></span>    |                                         <span data-ttu-id="e3c45-111">0</span><span class="sxs-lookup"><span data-stu-id="e3c45-111">0</span></span>                                          |
|  <span data-ttu-id="e3c45-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="e3c45-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="e3c45-113">0</span><span class="sxs-lookup"><span data-stu-id="e3c45-113">0</span></span>                                          |
|  <span data-ttu-id="e3c45-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="e3c45-114">Message Text</span></span>   |       <span data-ttu-id="e3c45-115">サービス証明書の拇印が無効です。40 桁の 16 進数が必要です。</span><span class="sxs-lookup"><span data-stu-id="e3c45-115">Invalid service certificate thumbprint; expected 40 hexadecimal digits</span></span>       |
  
## <a name="explanation"></a><span data-ttu-id="e3c45-116">説明</span><span class="sxs-lookup"><span data-stu-id="e3c45-116">Explanation</span></span>  
 <span data-ttu-id="e3c45-117">無効なサービス証明書の拇印が指定されました。</span><span class="sxs-lookup"><span data-stu-id="e3c45-117">An invalid service certificate thumbprint was specified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e3c45-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="e3c45-118">User Action</span></span>  
 <span data-ttu-id="e3c45-119">WCF ポートを構成するコードで、ユーザー インターフェイスのサービス証明書プロパティには、16 進の 40 桁の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="e3c45-119">In the code configuring the WCF port, the service certificate property of the user interface expects a hexadecimal 40-digit value.</span></span> <span data-ttu-id="e3c45-120">例: 798A68E7A3E6F2CCC6929FC4AF2A15A9EED66E39</span><span class="sxs-lookup"><span data-stu-id="e3c45-120">Example: 798A68E7A3E6F2CCC6929FC4AF2A15A9EED66E39</span></span>  
  
 <span data-ttu-id="e3c45-121">証明書の詳細については、次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3c45-121">For additional information on certificates, see the following resource:</span></span>  
  
-   [<span data-ttu-id="e3c45-122">WCF アダプターの証明書のインストール</span><span class="sxs-lookup"><span data-stu-id="e3c45-122">Installing Certificates for the WCF Adapters</span></span>](../core/installing-certificates-for-the-wcf-adapters.md)
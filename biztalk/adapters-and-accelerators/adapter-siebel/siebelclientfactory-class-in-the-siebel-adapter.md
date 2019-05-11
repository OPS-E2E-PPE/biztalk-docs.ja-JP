---
title: Siebel アダプターの SiebelClientFactory クラス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SiebelClientFactory
- Data Provider for Siebel, SiebelClientFactory
- SiebelClientFactory, supported properties and methods
ms.assetid: f3a807d3-a030-47d8-b145-e18075ec353c
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c732d029e1c3866caf5d20f11a790b80bc40cf68
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370704"
---
# <a name="siebelclientfactory-class-in-the-siebel-adapter"></a><span data-ttu-id="e0038-102">Siebel アダプターの SiebelClientFactory クラス</span><span class="sxs-lookup"><span data-stu-id="e0038-102">SiebelClientFactory class in the Siebel adapter</span></span>
<span data-ttu-id="e0038-103">ADO.NET クライアントにアクセスする、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]ジェネリックの ADO.NET クラスとインターフェイスを使用します。</span><span class="sxs-lookup"><span data-stu-id="e0038-103">An ADO.NET client accesses the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] using generic ADO.NET classes and interfaces.</span></span> <span data-ttu-id="e0038-104">この機能を有効にする、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]継承、 **System.Data.Common.DbProviderFactory**クラス。</span><span class="sxs-lookup"><span data-stu-id="e0038-104">To enable this feature, the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] inherits the **System.Data.Common.DbProviderFactory** class.</span></span> <span data-ttu-id="e0038-105">クライアント プログラムは、次のようにクライアントを使用します。</span><span class="sxs-lookup"><span data-stu-id="e0038-105">The client program consumes the client as follows:</span></span>  
  
```  
  
DbProviderFactory factory = DbProviderFactories.GetFactory("Microsoft.Data.SiebelClient");  
DbConnection connection = factory.CreateConnection();  
```  
  
 <span data-ttu-id="e0038-106">その他の方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e0038-106">An alternative approach is as follows:</span></span>  
  
```  
SiebelClientFactory factory = SiebelClientFactory.Instance;  
DbConnection connection = factory.CreateConnection();  
```  
  
 <span data-ttu-id="e0038-107">SiebelClientFactory は Microsoft.Data.SiebelClient 名前空間に存在します。</span><span class="sxs-lookup"><span data-stu-id="e0038-107">SiebelClientFactory exists in the namespace Microsoft.Data.SiebelClient.</span></span>  
  
## <a name="supported-members"></a><span data-ttu-id="e0038-108">サポートされているメンバー</span><span class="sxs-lookup"><span data-stu-id="e0038-108">Supported Members</span></span>  
 <span data-ttu-id="e0038-109">**SiebelClientFactory**拡張**System.Data.CommonDbProviderFactory**します。</span><span class="sxs-lookup"><span data-stu-id="e0038-109">**SiebelClientFactory** extends **System.Data.CommonDbProviderFactory**.</span></span>  <span data-ttu-id="e0038-110">次の表は、メンバーの説明を**SiebelClientFactory**よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="e0038-110">The following table provides a description of the members that **SiebelClientFactory** overrides.</span></span>  
  
|<span data-ttu-id="e0038-111">名前</span><span class="sxs-lookup"><span data-stu-id="e0038-111">Name</span></span>|<span data-ttu-id="e0038-112">説明</span><span class="sxs-lookup"><span data-stu-id="e0038-112">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="e0038-113">**インスタンス**</span><span class="sxs-lookup"><span data-stu-id="e0038-113">**Instance**</span></span>|<span data-ttu-id="e0038-114">これは、メンバー変数です。</span><span class="sxs-lookup"><span data-stu-id="e0038-114">This is a member variable.</span></span>  <span data-ttu-id="e0038-115">SiebelClientFactory のシングルトン インスタンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="e0038-115">It provides a singleton instance of SiebelClientFactory.</span></span>|  
|<span data-ttu-id="e0038-116">**CreateCommand()**</span><span class="sxs-lookup"><span data-stu-id="e0038-116">**CreateCommand()**</span></span>|<span data-ttu-id="e0038-117">SiebelCommand のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e0038-117">Creates an instance of SiebelCommand.</span></span>|  
|<span data-ttu-id="e0038-118">**CreateConnection()**</span><span class="sxs-lookup"><span data-stu-id="e0038-118">**CreateConnection()**</span></span>|<span data-ttu-id="e0038-119">SiebelConnection のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e0038-119">Creates an instance of SiebelConnection.</span></span>|  
|<span data-ttu-id="e0038-120">**CreateConnectionStringBuilder()**</span><span class="sxs-lookup"><span data-stu-id="e0038-120">**CreateConnectionStringBuilder()**</span></span>|<span data-ttu-id="e0038-121">SiebelConnectionStringBuilder のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e0038-121">Creates an instance of SiebelConnectionStringBuilder.</span></span>|  
|<span data-ttu-id="e0038-122">**CreateParameter()**</span><span class="sxs-lookup"><span data-stu-id="e0038-122">**CreateParameter()**</span></span>|<span data-ttu-id="e0038-123">SiebelParameter のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e0038-123">Creates an instance of SiebelParameter.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e0038-124">参照</span><span class="sxs-lookup"><span data-stu-id="e0038-124">See Also</span></span>  
 [<span data-ttu-id="e0038-125">Siebel アダプターを使用した ADO.NET インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="e0038-125">Extend ADO.NET Interfaces with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)
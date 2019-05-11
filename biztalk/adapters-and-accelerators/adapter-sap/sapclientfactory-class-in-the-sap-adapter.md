---
title: SAP アダプターの SAPClientFactory クラス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAPClientFactory, supported methods and classes
ms.assetid: e64de5e4-e53f-4708-ab02-9e12774e94cd
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9920403c0ce260bed686640227c4d05923563f4e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372980"
---
# <a name="sapclientfactory-class-in-the-sap-adapter"></a><span data-ttu-id="84e37-102">SAP アダプターの SAPClientFactory クラス</span><span class="sxs-lookup"><span data-stu-id="84e37-102">SAPClientFactory class in the SAP adapter</span></span>
<span data-ttu-id="84e37-103">メソッドおよびプロパティを次のセクションの一覧、 **SAPClientFactory**クラス。</span><span class="sxs-lookup"><span data-stu-id="84e37-103">The following section lists the methods and properties for the **SAPClientFactory** class.</span></span> <span data-ttu-id="84e37-104">これは、派生元**System.Data.Common.DbProviderFactory**します。</span><span class="sxs-lookup"><span data-stu-id="84e37-104">This is derived from **System.Data.Common.DbProviderFactory**.</span></span>  
  
## <a name="supported-properties"></a><span data-ttu-id="84e37-105">サポートされているプロパティ</span><span class="sxs-lookup"><span data-stu-id="84e37-105">Supported Properties</span></span>  
  
|<span data-ttu-id="84e37-106">名前</span><span class="sxs-lookup"><span data-stu-id="84e37-106">Name</span></span>|<span data-ttu-id="84e37-107">Get/Set</span><span class="sxs-lookup"><span data-stu-id="84e37-107">Get/Set</span></span>|<span data-ttu-id="84e37-108">説明</span><span class="sxs-lookup"><span data-stu-id="84e37-108">Description</span></span>|  
|----------|--------------|-----------------|  
|<span data-ttu-id="84e37-109">**インスタンス**</span><span class="sxs-lookup"><span data-stu-id="84e37-109">**Instance**</span></span>|-|<span data-ttu-id="84e37-110">SAPClientFactory のシングルトン インスタンス</span><span class="sxs-lookup"><span data-stu-id="84e37-110">Singleton instance of SAPClientFactory</span></span>|  
  
## <a name="supported-methods"></a><span data-ttu-id="84e37-111">サポートされているメソッド</span><span class="sxs-lookup"><span data-stu-id="84e37-111">Supported Methods</span></span>  
  
|<span data-ttu-id="84e37-112">名前</span><span class="sxs-lookup"><span data-stu-id="84e37-112">Name</span></span>|<span data-ttu-id="84e37-113">説明</span><span class="sxs-lookup"><span data-stu-id="84e37-113">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="84e37-114">**CreateCommand()**</span><span class="sxs-lookup"><span data-stu-id="84e37-114">**CreateCommand()**</span></span>|<span data-ttu-id="84e37-115">SAPCommand のインスタンスを作成します</span><span class="sxs-lookup"><span data-stu-id="84e37-115">Creates an instance of SAPCommand</span></span>|  
|<span data-ttu-id="84e37-116">**CreateConnection()**</span><span class="sxs-lookup"><span data-stu-id="84e37-116">**CreateConnection()**</span></span>|<span data-ttu-id="84e37-117">SAPConnection のインスタンスを作成します</span><span class="sxs-lookup"><span data-stu-id="84e37-117">Creates an instance of SAPConnection</span></span>|  
|<span data-ttu-id="84e37-118">**CreateConnectionStringBuilder()**</span><span class="sxs-lookup"><span data-stu-id="84e37-118">**CreateConnectionStringBuilder()**</span></span>|<span data-ttu-id="84e37-119">SAPConnectionStringBuilder のインスタンスを作成します</span><span class="sxs-lookup"><span data-stu-id="84e37-119">Creates an instance of SAPConnectionStringBuilder</span></span>|  
|<span data-ttu-id="84e37-120">**CreateParameter()**</span><span class="sxs-lookup"><span data-stu-id="84e37-120">**CreateParameter()**</span></span>|<span data-ttu-id="84e37-121">SAPParameter のインスタンスを作成します</span><span class="sxs-lookup"><span data-stu-id="84e37-121">Creates an instance of SAPParameter</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="84e37-122">参照</span><span class="sxs-lookup"><span data-stu-id="84e37-122">See Also</span></span>  
 [<span data-ttu-id="84e37-123">SAP アダプターを使用した ADO.NET インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="84e37-123">Extend ADO.NET Interfaces with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)
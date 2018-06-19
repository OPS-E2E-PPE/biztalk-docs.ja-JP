---
title: SAP アダプターで SAPClientFactory クラス |Microsoft ドキュメント
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
ms.openlocfilehash: 3c82e4bea6a16085608ebf1f8fe10ea95b4db394
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217634"
---
# <a name="sapclientfactory-class-in-the-sap-adapter"></a><span data-ttu-id="e2027-102">SAP アダプターで SAPClientFactory クラス</span><span class="sxs-lookup"><span data-stu-id="e2027-102">SAPClientFactory class in the SAP adapter</span></span>
<span data-ttu-id="e2027-103">次のセクションではメソッドとプロパティの一覧表示、 **SAPClientFactory**クラスです。</span><span class="sxs-lookup"><span data-stu-id="e2027-103">The following section lists the methods and properties for the **SAPClientFactory** class.</span></span> <span data-ttu-id="e2027-104">これは、派生元**System.Data.Common.DbProviderFactory**です。</span><span class="sxs-lookup"><span data-stu-id="e2027-104">This is derived from **System.Data.Common.DbProviderFactory**.</span></span>  
  
## <a name="supported-properties"></a><span data-ttu-id="e2027-105">サポートされているプロパティ</span><span class="sxs-lookup"><span data-stu-id="e2027-105">Supported Properties</span></span>  
  
|<span data-ttu-id="e2027-106">名前</span><span class="sxs-lookup"><span data-stu-id="e2027-106">Name</span></span>|<span data-ttu-id="e2027-107">取得/設定</span><span class="sxs-lookup"><span data-stu-id="e2027-107">Get/Set</span></span>|<span data-ttu-id="e2027-108">Description</span><span class="sxs-lookup"><span data-stu-id="e2027-108">Description</span></span>|  
|----------|--------------|-----------------|  
|<span data-ttu-id="e2027-109">**インスタンス**</span><span class="sxs-lookup"><span data-stu-id="e2027-109">**Instance**</span></span>|-|<span data-ttu-id="e2027-110">SAPClientFactory のシングルトン インスタンス</span><span class="sxs-lookup"><span data-stu-id="e2027-110">Singleton instance of SAPClientFactory</span></span>|  
  
## <a name="supported-methods"></a><span data-ttu-id="e2027-111">サポートされているメソッド</span><span class="sxs-lookup"><span data-stu-id="e2027-111">Supported Methods</span></span>  
  
|<span data-ttu-id="e2027-112">名前</span><span class="sxs-lookup"><span data-stu-id="e2027-112">Name</span></span>|<span data-ttu-id="e2027-113">Description</span><span class="sxs-lookup"><span data-stu-id="e2027-113">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="e2027-114">**CreateCommand()**</span><span class="sxs-lookup"><span data-stu-id="e2027-114">**CreateCommand()**</span></span>|<span data-ttu-id="e2027-115">SAPCommand のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e2027-115">Creates an instance of SAPCommand</span></span>|  
|<span data-ttu-id="e2027-116">**CreateConnection()**</span><span class="sxs-lookup"><span data-stu-id="e2027-116">**CreateConnection()**</span></span>|<span data-ttu-id="e2027-117">SAPConnection のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e2027-117">Creates an instance of SAPConnection</span></span>|  
|<span data-ttu-id="e2027-118">**CreateConnectionStringBuilder()**</span><span class="sxs-lookup"><span data-stu-id="e2027-118">**CreateConnectionStringBuilder()**</span></span>|<span data-ttu-id="e2027-119">SAPConnectionStringBuilder のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e2027-119">Creates an instance of SAPConnectionStringBuilder</span></span>|  
|<span data-ttu-id="e2027-120">**CreateParameter()**</span><span class="sxs-lookup"><span data-stu-id="e2027-120">**CreateParameter()**</span></span>|<span data-ttu-id="e2027-121">SAPParameter のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e2027-121">Creates an instance of SAPParameter</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e2027-122">参照</span><span class="sxs-lookup"><span data-stu-id="e2027-122">See Also</span></span>  
 [<span data-ttu-id="e2027-123">SAP アダプターと ADO.NET インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="e2027-123">Extend ADO.NET Interfaces with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)
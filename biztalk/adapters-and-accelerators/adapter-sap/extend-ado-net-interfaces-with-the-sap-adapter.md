---
title: SAP アダプターを使用した ADO.NET インターフェイスの拡張 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ADO.NET interfaces, extending
ms.assetid: ed7524ff-fc1a-4668-87a5-2d2e806a5d27
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13b461743743049f9e276b3086ef6424c95cecd5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373439"
---
# <a name="extend-adonet-interfaces-with-the-sap-adapter"></a><span data-ttu-id="1f561-102">SAP アダプターを使用した ADO.NET インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="1f561-102">Extend ADO.NET Interfaces with the SAP adapter</span></span>
<span data-ttu-id="1f561-103">[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]) さまざまな ADO.NET インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="1f561-103">The [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]) extends various ADO.NET interfaces.</span></span> <span data-ttu-id="1f561-104">ADO.NET クライアントは、SAP システムとのインターフェイスにこれらを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1f561-104">The ADO.NET clients can use these to interface with the SAP system.</span></span> <span data-ttu-id="1f561-105">このセクションでは、これらのインターフェイスの詳細について提供します。</span><span class="sxs-lookup"><span data-stu-id="1f561-105">This section provides more information about these interfaces.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1f561-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1f561-106">In This Section</span></span>  
  
-   [<span data-ttu-id="1f561-107">SAP アダプターの SAPConnection クラス</span><span class="sxs-lookup"><span data-stu-id="1f561-107">SAPConnection class in the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/sapconnection-class-in-the-sap-adapter.md)  
  
-   [<span data-ttu-id="1f561-108">SAP アダプターの SAPCommand クラス</span><span class="sxs-lookup"><span data-stu-id="1f561-108">SAPCommand class in the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/sapcommand-class-in-the-sap-adapter.md)  
  
-   [<span data-ttu-id="1f561-109">SAP アダプターの SAPDataReader クラス</span><span class="sxs-lookup"><span data-stu-id="1f561-109">SAPDataReader class in the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/sapdatareader-class-in-the-sap-adapter.md)  
  
-   [<span data-ttu-id="1f561-110">SAP アダプターの SAPParameter クラス</span><span class="sxs-lookup"><span data-stu-id="1f561-110">SAPParameter class in the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/sapparameter-class-in-the-sap-adapter.md)  
  
-   [<span data-ttu-id="1f561-111">SAP アダプターの SAPParameterCollection クラス</span><span class="sxs-lookup"><span data-stu-id="1f561-111">SAPParameterCollection class in the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/sapparametercollection-class-in-the-sap-adapter.md)  
  
-   [<span data-ttu-id="1f561-112">SAP アダプターの SAPClientFactory クラス</span><span class="sxs-lookup"><span data-stu-id="1f561-112">SAPClientFactory class in the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/sapclientfactory-class-in-the-sap-adapter.md)
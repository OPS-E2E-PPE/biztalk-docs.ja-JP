---
title: "Siebel eBusiness Applications の .NET Framework データ プロバイダーを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ADO.NET programming, performing operations
- Data Provider for Siebel, overview
ms.assetid: 97fe4f95-c9ae-42f1-a159-1b0e98607b31
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5acb8f96add3dcde48456751d82dc2a8e00ffe43
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="use-the-net-framework-data-provider-for-siebel-ebusiness-applications"></a><span data-ttu-id="7fb77-102">Siebel eBusiness Applications の .NET Framework データ プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="7fb77-102">Use the .NET Framework Data Provider for Siebel eBusiness Applications</span></span>
<span data-ttu-id="7fb77-103">このセクションの内容については、手順を使用して、 [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="7fb77-103">This section provides instructions on using the [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]).</span></span> <span data-ttu-id="7fb77-104">このセクションでは、に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="7fb77-104">This section provides information about:</span></span>  
  
-   <span data-ttu-id="7fb77-105">ADO.NET クライアントを使用して、Siebel システムへの接続への接続文字列。</span><span class="sxs-lookup"><span data-stu-id="7fb77-105">The connection string to connect to a Siebel system using an ADO.NET client.</span></span>  
  
-   <span data-ttu-id="7fb77-106">SELECT ステートメントおよび EXEC ステートメントの構文です。</span><span class="sxs-lookup"><span data-stu-id="7fb77-106">The syntax for SELECT and EXEC statements.</span></span>  
  
-   <span data-ttu-id="7fb77-107">使用して、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]と SSIS します。</span><span class="sxs-lookup"><span data-stu-id="7fb77-107">Using the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] with SSIS.</span></span>  
  
-   <span data-ttu-id="7fb77-108">ADO.NET のインターフェイスを[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]を拡張します。</span><span class="sxs-lookup"><span data-stu-id="7fb77-108">The ADO.NET interfaces that the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] extends.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7fb77-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7fb77-109">In This Section</span></span>  
  
-   [<span data-ttu-id="7fb77-110">Siebel アダプターと ADO.NET インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="7fb77-110">Extend ADO.NET Interfaces with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)  
  
-   [<span data-ttu-id="7fb77-111">Siebel の接続文字列のデータ プロバイダーのプロパティ</span><span class="sxs-lookup"><span data-stu-id="7fb77-111">Data Provider properties for the Siebel Connection String</span></span>](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md)  
  
-   [<span data-ttu-id="7fb77-112">Siebel の SELECT ステートメントの構文</span><span class="sxs-lookup"><span data-stu-id="7fb77-112">Syntax for a SELECT Statement in Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md)  
  
-   [<span data-ttu-id="7fb77-113">Siebel の EXEC ステートメントの構文</span><span class="sxs-lookup"><span data-stu-id="7fb77-113">Syntax for an EXEC Statement in Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/syntax-for-an-exec-statement-in-siebel.md)  
  
-   [<span data-ttu-id="7fb77-114">Siebel ビジネス コンポーネントで SELECT クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="7fb77-114">Run a SELECT Query on Business Components with Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/run-a-select-query-on-business-components-with-siebel.md)  
  
-   [<span data-ttu-id="7fb77-115">Siebel ビジネス サービスの実行操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="7fb77-115">Run an EXECUTE Operation on Business Services with Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/run-an-execute-operation-on-business-services-with-siebel.md)  
  
-   [<span data-ttu-id="7fb77-116">Siebel と SSIS のデータ プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="7fb77-116">Use the Data Provider for Siebel with SSIS</span></span>](../../adapters-and-accelerators/adapter-siebel/use-the-data-provider-for-siebel-with-ssis.md)
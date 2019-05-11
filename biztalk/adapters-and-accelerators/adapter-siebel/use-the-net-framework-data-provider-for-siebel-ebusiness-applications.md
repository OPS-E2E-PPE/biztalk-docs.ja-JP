---
title: .NET Framework データ プロバイダーを使用して、Siebel eBusiness Applications の |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ADO.NET programming, performing operations
- Data Provider for Siebel, overview
ms.assetid: 97fe4f95-c9ae-42f1-a159-1b0e98607b31
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70d3d3850480cd3d3af8e0942590d919902b4378
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370239"
---
# <a name="use-the-net-framework-data-provider-for-siebel-ebusiness-applications"></a><span data-ttu-id="e1dd8-102">.NET Framework Data Provider 用 Siebel eBusiness Applications を使用して、</span><span class="sxs-lookup"><span data-stu-id="e1dd8-102">Use the .NET Framework Data Provider for Siebel eBusiness Applications</span></span>
<span data-ttu-id="e1dd8-103">このセクションで使用方法については、 [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="e1dd8-103">This section provides instructions on using the [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]).</span></span> <span data-ttu-id="e1dd8-104">このセクションでは、に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="e1dd8-104">This section provides information about:</span></span>  
  
- <span data-ttu-id="e1dd8-105">ADO.NET クライアントを使用して Siebel システムに接続する接続文字列。</span><span class="sxs-lookup"><span data-stu-id="e1dd8-105">The connection string to connect to a Siebel system using an ADO.NET client.</span></span>  
  
- <span data-ttu-id="e1dd8-106">SELECT ステートメントと EXEC ステートメントの構文です。</span><span class="sxs-lookup"><span data-stu-id="e1dd8-106">The syntax for SELECT and EXEC statements.</span></span>  
  
- <span data-ttu-id="e1dd8-107">使用して、 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] SSIS を使用します。</span><span class="sxs-lookup"><span data-stu-id="e1dd8-107">Using the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] with SSIS.</span></span>  
  
- <span data-ttu-id="e1dd8-108">ADO.NET インターフェイスを[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]を拡張します。</span><span class="sxs-lookup"><span data-stu-id="e1dd8-108">The ADO.NET interfaces that the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] extends.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e1dd8-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e1dd8-109">In This Section</span></span>  
  
-   [<span data-ttu-id="e1dd8-110">Siebel アダプターを使用した ADO.NET インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="e1dd8-110">Extend ADO.NET Interfaces with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)  
  
-   [<span data-ttu-id="e1dd8-111">Siebel 接続文字列のデータ プロバイダーのプロパティ</span><span class="sxs-lookup"><span data-stu-id="e1dd8-111">Data Provider properties for the Siebel Connection String</span></span>](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md)  
  
-   [<span data-ttu-id="e1dd8-112">Siebel の SELECT ステートメントの構文</span><span class="sxs-lookup"><span data-stu-id="e1dd8-112">Syntax for a SELECT Statement in Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md)  
  
-   [<span data-ttu-id="e1dd8-113">Siebel の EXEC ステートメントの構文</span><span class="sxs-lookup"><span data-stu-id="e1dd8-113">Syntax for an EXEC Statement in Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/syntax-for-an-exec-statement-in-siebel.md)  
  
-   [<span data-ttu-id="e1dd8-114">Siebel ビジネス コンポーネントで SELECT クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="e1dd8-114">Run a SELECT Query on Business Components with Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/run-a-select-query-on-business-components-with-siebel.md)  
  
-   [<span data-ttu-id="e1dd8-115">Siebel ビジネス サービスに対して EXECUTE 操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="e1dd8-115">Run an EXECUTE Operation on Business Services with Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/run-an-execute-operation-on-business-services-with-siebel.md)  
  
-   [<span data-ttu-id="e1dd8-116">Data Provider for Siebel を SSIS と一緒に使用する</span><span class="sxs-lookup"><span data-stu-id="e1dd8-116">Use the Data Provider for Siebel with SSIS</span></span>](../../adapters-and-accelerators/adapter-siebel/use-the-data-provider-for-siebel-with-ssis.md)
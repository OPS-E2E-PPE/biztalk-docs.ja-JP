---
title: データ プロバイダーを使用して、SSIS を使用した SAP の |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for SAP, using with SSIS
- SSIS, Data Provider for SAP
ms.assetid: e8c50cc1-ac25-4993-9aee-7fd88268d65d
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d75ea62e0cb8edb39f655e1e763c1855e19f46a8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372234"
---
# <a name="use-the-data-provider-for-sap-with-ssis"></a><span data-ttu-id="e1f4d-102">SSIS を使用した SAP のデータ プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="e1f4d-102">Use the Data Provider for SAP with SSIS</span></span>
<span data-ttu-id="e1f4d-103">使用することができます、[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]と共に SQL Server Integration Service (SSIS)、SAP システムから SQL Server データベース テーブルにデータをインポートする、フラット ファイル、またはその他の互換性のある変換先の型。</span><span class="sxs-lookup"><span data-stu-id="e1f4d-103">You can use the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] along with SQL Server Integration Service (SSIS) to import data from an SAP system into SQL Server database tables, flat files, or other compatible destination types.</span></span> <span data-ttu-id="e1f4d-104">SAP システムからデータをインポートする実行可能な SSIS パッケージを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="e1f4d-104">You can create an SSIS package that can be executed to import data from an SAP system.</span></span>  
  
 <span data-ttu-id="e1f4d-105">SQL Server インポートおよびエクスポート ウィザードを使用して、SQL Server データベースにデータをインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1f4d-105">You must use the SQL Server Import and Export wizard to import data into the SQL Server database.</span></span> <span data-ttu-id="e1f4d-106">インポートするデータを指定するクエリを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1f4d-106">You must provide a query to specify data to be imported.</span></span> <span data-ttu-id="e1f4d-107">SELECT ステートメントまたは EXECQUERY ステートメントを使用してクエリを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="e1f4d-107">You can specify a query using the SELECT statement or the EXECQUERY statement.</span></span> <span data-ttu-id="e1f4d-108">サポートされているセマンティクスへのクエリを確認する必要があります、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="e1f4d-108">The query must confirm to the semantics supported by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span> <span data-ttu-id="e1f4d-109">クエリの SELECT、文法の詳細については、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を参照してください[SAP で SELECT ステートメントの構文](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md)します。</span><span class="sxs-lookup"><span data-stu-id="e1f4d-109">For more information about the grammar for a SELECT query for the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Syntax for a SELECT Statement in SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md).</span></span> <span data-ttu-id="e1f4d-110">EXECQUERY ステートメントの文法の詳細については、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を参照してください[sap EXECQUERY ステートメントの構文](../../adapters-and-accelerators/adapter-sap/syntax-for-an-execquery-statement-in-sap.md)します。</span><span class="sxs-lookup"><span data-stu-id="e1f4d-110">For more information about the grammar for an EXECQUERY statement for the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Syntax for an EXECQUERY Statement in SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-an-execquery-statement-in-sap.md).</span></span>  
  
 <span data-ttu-id="e1f4d-111">SQL Server インポート/エクスポート ウィザードは、SQL Server Management Studio または Visual Studio での統合サービス プロジェクトを開始できます。</span><span class="sxs-lookup"><span data-stu-id="e1f4d-111">You can start the SQL Server Import Export wizard either from the SQL Server Management Studio or from an Integration Service project in Visual Studio.</span></span> <span data-ttu-id="e1f4d-112">このセクションでは、Management Studio と Visual Studio の両方のインターフェイスから、ウィザードの実行について説明します。</span><span class="sxs-lookup"><span data-stu-id="e1f4d-112">This section provides instructions on running the wizard from both the Management Studio and Visual Studio interfaces.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e1f4d-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e1f4d-113">In This Section</span></span>  
  
-   [<span data-ttu-id="e1f4d-114">SQL Server Management Studio を使用して SAP のデータをインポートする</span><span class="sxs-lookup"><span data-stu-id="e1f4d-114">Import SAP Data Using SQL Server Management Studio</span></span>](../../adapters-and-accelerators/adapter-sap/import-sap-data-using-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="e1f4d-115">Visual Studio を使用して SAP のデータをインポートする</span><span class="sxs-lookup"><span data-stu-id="e1f4d-115">Import SAP Data Using Visual Studio</span></span>](../../adapters-and-accelerators/adapter-sap/import-sap-data-using-visual-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="e1f4d-116">参照</span><span class="sxs-lookup"><span data-stu-id="e1f4d-116">See Also</span></span>  
 [<span data-ttu-id="e1f4d-117">.NET Framework Data Provider for mySAP Business Suite の使用</span><span class="sxs-lookup"><span data-stu-id="e1f4d-117">Use the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)
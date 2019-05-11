---
title: データ プロバイダーを使用して、Siebel を SSIS と一緒にの |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSIS
- SQL Server Integration Services
- Data Provider for Siebel, using with SSIS
ms.assetid: e72cecf2-6c05-4df7-8e6e-aff3a9df8b79
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 999583cf09c663e847a6ae680736af9aea581726
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370257"
---
# <a name="use-the-data-provider-for-siebel-with-ssis"></a><span data-ttu-id="6dbdd-102">Siebel を SSIS と一緒に用データ プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="6dbdd-102">Use the Data Provider for Siebel with SSIS</span></span>
<span data-ttu-id="6dbdd-103">使用することができます、 [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]) と共に SQL Server Integration Services (SSIS) Siebel システムから SQL Server データベース テーブルにデータをインポートする、フラット ファイル、またはその他の互換性のある変換先の型。</span><span class="sxs-lookup"><span data-stu-id="6dbdd-103">You can use the [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]) along with SQL Server Integration Services (SSIS) to import data from a Siebel system into SQL Server database tables, flat files, or other compatible destination types.</span></span> <span data-ttu-id="6dbdd-104">具体的には、このデータをインポートする実行可能な SSIS パッケージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="6dbdd-104">Specifically, you can create an SSIS package that can be executed to import this data.</span></span>  
  
 <span data-ttu-id="6dbdd-105">SQL Server データベースにデータをインポート、SQL Server インポートおよびエクスポート ウィザードを使用してインポートするデータを指定する SELECT クエリを提供します。</span><span class="sxs-lookup"><span data-stu-id="6dbdd-105">To import data into the SQL Server database, use the SQL Server Import and Export Wizard, and provide a SELECT query to specify the data to be imported.</span></span> <span data-ttu-id="6dbdd-106">サポートされているセマンティクスへのクエリを確認する必要があります、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="6dbdd-106">The query must confirm to the semantics supported by the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)].</span></span> <span data-ttu-id="6dbdd-107">クエリの SELECT、文法の詳細については、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]を参照してください[Siebel の SELECT ステートメントの構文](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md)します。</span><span class="sxs-lookup"><span data-stu-id="6dbdd-107">For more information about the grammar for a SELECT query for the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], see [Syntax for a SELECT Statement in Siebel](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6dbdd-108">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] EXEC ステートメント SSIS の使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="6dbdd-108">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] does not support using an EXEC statement with SSIS.</span></span>  
  
 <span data-ttu-id="6dbdd-109">SQL Server インポートおよびエクスポート ウィザードは、SQL Server Management Studio または Visual Studio での統合サービス プロジェクトを開始できます。</span><span class="sxs-lookup"><span data-stu-id="6dbdd-109">You can start the SQL Server Import and Export wizard either from the SQL Server Management Studio or from an Integration Service project in Visual Studio.</span></span> <span data-ttu-id="6dbdd-110">このセクションでは、SQL Server Management Studio と Visual Studio の両方のインターフェイスから、ウィザードの実行について説明します。</span><span class="sxs-lookup"><span data-stu-id="6dbdd-110">This section provides instructions on running the wizard from both the SQL Server Management Studio and Visual Studio interfaces.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6dbdd-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6dbdd-111">In This Section</span></span>  
  
-   [<span data-ttu-id="6dbdd-112">SQL Server Management Studio を使用して Siebel データをインポートする</span><span class="sxs-lookup"><span data-stu-id="6dbdd-112">Import Siebel Data Using SQL Server Management Studio</span></span>](../../adapters-and-accelerators/adapter-siebel/import-siebel-data-using-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="6dbdd-113">Visual Studio を使用して Siebel データをインポートする</span><span class="sxs-lookup"><span data-stu-id="6dbdd-113">Import Siebel Data Using Visual Studio</span></span>](../../adapters-and-accelerators/adapter-siebel/import-siebel-data-using-visual-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="6dbdd-114">参照</span><span class="sxs-lookup"><span data-stu-id="6dbdd-114">See Also</span></span>  
 [<span data-ttu-id="6dbdd-115">.NET Framework Data Provider for Siebel eBusiness Applications を使用する</span><span class="sxs-lookup"><span data-stu-id="6dbdd-115">Use the .NET Framework Data Provider for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)
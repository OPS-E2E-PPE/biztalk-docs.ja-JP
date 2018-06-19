---
title: Siebel と SSIS のデータ プロバイダーを使用して |Microsoft ドキュメント
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
ms.openlocfilehash: a0c46c1437d7eeedd56ee37b054f9f6eb6b72ada
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222210"
---
# <a name="use-the-data-provider-for-siebel-with-ssis"></a><span data-ttu-id="5be52-102">Siebel と SSIS のデータ プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="5be52-102">Use the Data Provider for Siebel with SSIS</span></span>
<span data-ttu-id="5be52-103">使用することができます、 [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]) と共に SQL Server Integration Services (SSIS) Siebel システムから SQL Server データベース テーブルにデータをインポートする、フラット ファイル、またはその他の互換性のある変換先の型。</span><span class="sxs-lookup"><span data-stu-id="5be52-103">You can use the [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]) along with SQL Server Integration Services (SSIS) to import data from a Siebel system into SQL Server database tables, flat files, or other compatible destination types.</span></span> <span data-ttu-id="5be52-104">具体的には、このデータをインポートする実行可能な SSIS パッケージを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="5be52-104">Specifically, you can create an SSIS package that can be executed to import this data.</span></span>  
  
 <span data-ttu-id="5be52-105">SQL Server データベースにデータをインポート、SQL Server インポートおよびエクスポート ウィザードを使用でき、SELECT クエリをインポートするデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="5be52-105">To import data into the SQL Server database, use the SQL Server Import and Export Wizard, and provide a SELECT query to specify the data to be imported.</span></span> <span data-ttu-id="5be52-106">サポートされているセマンティクスへのクエリを確認する必要があります、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="5be52-106">The query must confirm to the semantics supported by the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)].</span></span> <span data-ttu-id="5be52-107">クエリを SELECT の文法の詳細については、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]を参照してください[Siebel の SELECT ステートメントの構文](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md)です。</span><span class="sxs-lookup"><span data-stu-id="5be52-107">For more information about the grammar for a SELECT query for the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], see [Syntax for a SELECT Statement in Siebel](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5be52-108">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] SSIS で、EXEC ステートメントの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="5be52-108">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] does not support using an EXEC statement with SSIS.</span></span>  
  
 <span data-ttu-id="5be52-109">SQL Server Management Studio または Visual Studio での統合サービス プロジェクトから、SQL Server インポートおよびエクスポート ウィザードを開始することができます。</span><span class="sxs-lookup"><span data-stu-id="5be52-109">You can start the SQL Server Import and Export wizard either from the SQL Server Management Studio or from an Integration Service project in Visual Studio.</span></span> <span data-ttu-id="5be52-110">このセクションでは、SQL Server Management Studio および Visual Studio の両方のインターフェイスから、ウィザードの実行について説明します。</span><span class="sxs-lookup"><span data-stu-id="5be52-110">This section provides instructions on running the wizard from both the SQL Server Management Studio and Visual Studio interfaces.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5be52-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5be52-111">In This Section</span></span>  
  
-   [<span data-ttu-id="5be52-112">Siebel を SQL Server Management Studio を使用してデータをインポートします。</span><span class="sxs-lookup"><span data-stu-id="5be52-112">Import Siebel Data Using SQL Server Management Studio</span></span>](../../adapters-and-accelerators/adapter-siebel/import-siebel-data-using-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="5be52-113">Siebel を Visual Studio を使用してデータをインポートします。</span><span class="sxs-lookup"><span data-stu-id="5be52-113">Import Siebel Data Using Visual Studio</span></span>](../../adapters-and-accelerators/adapter-siebel/import-siebel-data-using-visual-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="5be52-114">参照</span><span class="sxs-lookup"><span data-stu-id="5be52-114">See Also</span></span>  
 [<span data-ttu-id="5be52-115">Siebel eBusiness Applications の .NET Framework データ プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="5be52-115">Use the .NET Framework Data Provider for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)
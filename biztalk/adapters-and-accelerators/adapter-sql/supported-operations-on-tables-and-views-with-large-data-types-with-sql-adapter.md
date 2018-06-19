---
title: テーブルと、SQL アダプターを使用して大規模なデータ型を含むビューでの操作 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 70f3b863-da3c-45b0-98f2-469a62286ebf
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1d6d2c52ce0772297bb2834c13f31a55d7b7a13
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223866"
---
# <a name="operations-on-tables-and-views-that-contain-large-data-types-using-the-sql-adapter"></a><span data-ttu-id="20152-102">テーブルと、SQL アダプターを使用して大規模なデータ型を含むビューでの操作</span><span class="sxs-lookup"><span data-stu-id="20152-102">Operations on tables and views that contain large data types using the SQL adapter</span></span>
<span data-ttu-id="20152-103">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]の次の SQL Server 大量のデータ型のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="20152-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] provides supports for the following SQL Server large data types:</span></span>  
  
-   <span data-ttu-id="20152-104">Varchar (max)</span><span class="sxs-lookup"><span data-stu-id="20152-104">Varchar(Max)</span></span>  
  
-   <span data-ttu-id="20152-105">Nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="20152-105">Nvarchar(Max)</span></span>  
  
-   <span data-ttu-id="20152-106">Varbinary (max)</span><span class="sxs-lookup"><span data-stu-id="20152-106">Varbinary(Max)</span></span>  
  
 <span data-ttu-id="20152-107">SQL Server から大きなデータ値を読み取る、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]選択操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="20152-107">To read large data values from SQL Server, the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] exposes the Select operation.</span></span>  
  
 <span data-ttu-id="20152-108">SQL Server に大きなデータ値を書き込む、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]型 varchar (max)、nvarchar (max) または varbinary (max) の列の名前を < column_name > がここでは、設定 < column_name > 操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="20152-108">To write large data values to SQL Server, the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] exposes the Set<column_name> operation, where <column_name> is the name of the column of type Varchar(Max), Nvarchar(Max) or Varbinary(Max).</span></span> <span data-ttu-id="20152-109">< Column_name > の設定操作では、アダプター クライアントが SQL Server 2008 で FILESTREAM データを記述することもできます。</span><span class="sxs-lookup"><span data-stu-id="20152-109">The Set<column_name> operation also allows adapter clients to write FILESTREAM data in SQL Server 2008.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20152-110">設定 < column_name > 操作は、テーブルと列を含む上記 3 つの大規模なデータ型のいずれかのビューに対してのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="20152-110">The Set<column_name> operation is available only for those tables and views that contain columns with any of the three large data types mentioned earlier.</span></span>  
  
 <span data-ttu-id="20152-111">大規模なデータ型が含まれている SQL Server のテーブルおよびビューの操作の実行の詳細については、次を参照してください。[テーブルとビューを SQL アダプターを使用して大規模なデータ型を含む Operations](../../adapters-and-accelerators/adapter-sql/supported-operations-on-tables-and-views-with-large-data-types-with-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="20152-111">For detailed information about performing operations on tables and views in SQL Server that contain large data types, see [Operations on tables and views that contain large data types using the SQL adapter](../../adapters-and-accelerators/adapter-sql/supported-operations-on-tables-and-views-with-large-data-types-with-sql-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20152-112">参照</span><span class="sxs-lookup"><span data-stu-id="20152-112">See Also</span></span>  
 [<span data-ttu-id="20152-113">アダプターを使用して SAP システムへの接続します。</span><span class="sxs-lookup"><span data-stu-id="20152-113">Connect to an SAP system using the adapter</span></span>](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)
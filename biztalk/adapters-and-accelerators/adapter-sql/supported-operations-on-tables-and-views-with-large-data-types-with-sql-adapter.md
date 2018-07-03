---
title: テーブルと、SQL アダプターを使用して大規模なデータ型を含むビューに対する操作 |Microsoft Docs
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
ms.openlocfilehash: d4f693b676c1e3c0675051e9d0faf685e8b9d8df
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021190"
---
# <a name="operations-on-tables-and-views-that-contain-large-data-types-using-the-sql-adapter"></a><span data-ttu-id="9de65-102">テーブルと、SQL アダプターを使用して大規模なデータ型を含むビューに対する操作</span><span class="sxs-lookup"><span data-stu-id="9de65-102">Operations on tables and views that contain large data types using the SQL adapter</span></span>
<span data-ttu-id="9de65-103">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]次の SQL Server の大量のデータ型のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="9de65-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] provides supports for the following SQL Server large data types:</span></span>  
  
- <span data-ttu-id="9de65-104">Varchar (max)</span><span class="sxs-lookup"><span data-stu-id="9de65-104">Varchar(Max)</span></span>  
  
- <span data-ttu-id="9de65-105">Nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="9de65-105">Nvarchar(Max)</span></span>  
  
- <span data-ttu-id="9de65-106">Varbinary (max)</span><span class="sxs-lookup"><span data-stu-id="9de65-106">Varbinary(Max)</span></span>  
  
  <span data-ttu-id="9de65-107">SQL Server から大きなデータ値を読み取る、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]選択操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="9de65-107">To read large data values from SQL Server, the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] exposes the Select operation.</span></span>  
  
  <span data-ttu-id="9de65-108">SQL Server に大きなデータ値を書き込む、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] < column_name > がの型 varchar (max)、nvarchar (max) または varbinary (max) 列の名前は、< column_name > の設定操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="9de65-108">To write large data values to SQL Server, the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] exposes the Set<column_name> operation, where <column_name> is the name of the column of type Varchar(Max), Nvarchar(Max) or Varbinary(Max).</span></span> <span data-ttu-id="9de65-109">< Column_name > の設定操作では、SQL Server 2008 で FILESTREAM データを書き込むアダプター クライアントもできます。</span><span class="sxs-lookup"><span data-stu-id="9de65-109">The Set<column_name> operation also allows adapter clients to write FILESTREAM data in SQL Server 2008.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9de65-110">< Column_name > の設定操作では、これらのテーブルとビューの前に説明した 3 つの大規模なデータ型のいずれかの列を含むのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="9de65-110">The Set<column_name> operation is available only for those tables and views that contain columns with any of the three large data types mentioned earlier.</span></span>  
  
 <span data-ttu-id="9de65-111">大規模なデータ型を含む SQL Server でのテーブルとビューで操作を実行する方法の詳細については、次を参照してください。[テーブルと、SQL アダプターを使用して大規模なデータ型を含むビューで操作](../../adapters-and-accelerators/adapter-sql/supported-operations-on-tables-and-views-with-large-data-types-with-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="9de65-111">For detailed information about performing operations on tables and views in SQL Server that contain large data types, see [Operations on tables and views that contain large data types using the SQL adapter](../../adapters-and-accelerators/adapter-sql/supported-operations-on-tables-and-views-with-large-data-types-with-sql-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9de65-112">参照</span><span class="sxs-lookup"><span data-stu-id="9de65-112">See Also</span></span>  
 [<span data-ttu-id="9de65-113">アダプターを使用して SAP システムへの接続します。</span><span class="sxs-lookup"><span data-stu-id="9de65-113">Connect to an SAP system using the adapter</span></span>](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)
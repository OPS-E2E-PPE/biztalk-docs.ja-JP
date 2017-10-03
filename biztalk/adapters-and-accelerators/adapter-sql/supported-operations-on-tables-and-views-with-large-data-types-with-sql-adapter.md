---
title: "テーブルと、SQL アダプターを使用して大規模なデータ型を含むビューでの操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 70f3b863-da3c-45b0-98f2-469a62286ebf
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1d6d2c52ce0772297bb2834c13f31a55d7b7a13
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="operations-on-tables-and-views-that-contain-large-data-types-using-the-sql-adapter"></a>テーブルと、SQL アダプターを使用して大規模なデータ型を含むビューでの操作
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]の次の SQL Server 大量のデータ型のサポートを提供します。  
  
-   Varchar (max)  
  
-   Nvarchar (max)  
  
-   Varbinary (max)  
  
 SQL Server から大きなデータ値を読み取る、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]選択操作を公開します。  
  
 SQL Server に大きなデータ値を書き込む、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]型 varchar (max)、nvarchar (max) または varbinary (max) の列の名前を < column_name > がここでは、設定 < column_name > 操作を公開します。 < Column_name > の設定操作では、アダプター クライアントが SQL Server 2008 で FILESTREAM データを記述することもできます。  
  
> [!NOTE]
>  設定 < column_name > 操作は、テーブルと列を含む上記 3 つの大規模なデータ型のいずれかのビューに対してのみ使用できます。  
  
 大規模なデータ型が含まれている SQL Server のテーブルおよびビューの操作の実行の詳細については、次を参照してください。[テーブルとビューを SQL アダプターを使用して大規模なデータ型を含む Operations](../../adapters-and-accelerators/adapter-sql/supported-operations-on-tables-and-views-with-large-data-types-with-sql-adapter.md)です。  
  
## <a name="see-also"></a>参照  
 [アダプターを使用して SAP システムへの接続します。](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)
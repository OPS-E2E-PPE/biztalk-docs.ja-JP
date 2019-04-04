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
# <a name="operations-on-tables-and-views-that-contain-large-data-types-using-the-sql-adapter"></a>テーブルと、SQL アダプターを使用して大規模なデータ型を含むビューに対する操作
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]次の SQL Server の大量のデータ型のサポートを提供します。  
  
- Varchar (max)  
  
- Nvarchar (max)  
  
- Varbinary (max)  
  
  SQL Server から大きなデータ値を読み取る、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]選択操作を公開します。  
  
  SQL Server に大きなデータ値を書き込む、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] < column_name > がの型 varchar (max)、nvarchar (max) または varbinary (max) 列の名前は、< column_name > の設定操作を公開します。 < Column_name > の設定操作では、SQL Server 2008 で FILESTREAM データを書き込むアダプター クライアントもできます。  
  
> [!NOTE]
>  < Column_name > の設定操作では、これらのテーブルとビューの前に説明した 3 つの大規模なデータ型のいずれかの列を含むのみ使用できます。  
  
 大規模なデータ型を含む SQL Server でのテーブルとビューで操作を実行する方法の詳細については、[テーブルと、SQL アダプターを使用して大規模なデータ型を含むビューで操作](../../adapters-and-accelerators/adapter-sql/supported-operations-on-tables-and-views-with-large-data-types-with-sql-adapter.md)を参照してください。  
  
## <a name="see-also"></a>参照  
 [アダプターを使用して SAP システムへの接続します。](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)
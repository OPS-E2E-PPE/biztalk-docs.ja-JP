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
# <a name="use-the-data-provider-for-sap-with-ssis"></a>SSIS を使用した SAP のデータ プロバイダーを使用します。
使用することができます、[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]と共に SQL Server Integration Service (SSIS)、SAP システムから SQL Server データベース テーブルにデータをインポートする、フラット ファイル、またはその他の互換性のある変換先の型。 SAP システムからデータをインポートする実行可能な SSIS パッケージを作成することができます。  
  
 SQL Server インポートおよびエクスポート ウィザードを使用して、SQL Server データベースにデータをインポートする必要があります。 インポートするデータを指定するクエリを指定する必要があります。 SELECT ステートメントまたは EXECQUERY ステートメントを使用してクエリを指定することができます。 サポートされているセマンティクスへのクエリを確認する必要があります、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]します。 クエリの SELECT、文法の詳細については、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を参照してください[SAP で SELECT ステートメントの構文](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md)します。 EXECQUERY ステートメントの文法の詳細については、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を参照してください[sap EXECQUERY ステートメントの構文](../../adapters-and-accelerators/adapter-sap/syntax-for-an-execquery-statement-in-sap.md)します。  
  
 SQL Server インポート/エクスポート ウィザードは、SQL Server Management Studio または Visual Studio での統合サービス プロジェクトを開始できます。 このセクションでは、Management Studio と Visual Studio の両方のインターフェイスから、ウィザードの実行について説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SQL Server Management Studio を使用して SAP のデータをインポートする](../../adapters-and-accelerators/adapter-sap/import-sap-data-using-sql-server-management-studio.md)  
  
-   [Visual Studio を使用して SAP のデータをインポートする](../../adapters-and-accelerators/adapter-sap/import-sap-data-using-visual-studio.md)  
  
## <a name="see-also"></a>参照  
 [.NET Framework Data Provider for mySAP Business Suite の使用](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)
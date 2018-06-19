---
title: データ プロバイダーを使用して SSIS での SAP 向け |Microsoft ドキュメント
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
ms.openlocfilehash: a8459453e153626b6a79a5dc5f57ce041ba67d1d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217346"
---
# <a name="use-the-data-provider-for-sap-with-ssis"></a>SAP と SSIS のデータ プロバイダーを使用します。
使用することができます、[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]と共に SQL Server の統合サービス (SSIS) データを SAP システムから SQL Server データベースのテーブルをインポートする、フラット ファイル、またはその他の互換性のある変換先の型。 SAP システムからデータをインポートする実行可能な SSIS パッケージを作成することができます。  
  
 SQL Server インポートおよびエクスポート ウィザードを使用して、SQL Server データベースにデータをインポートする必要があります。 インポートするデータを指定するクエリを指定する必要があります。 SELECT ステートメントまたは EXECQUERY ステートメントを使用してクエリを指定することができます。 サポートされているセマンティクスへのクエリを確認する必要があります、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]です。 クエリを SELECT の文法の詳細については、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を参照してください[SAP の SELECT ステートメントの構文](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md)です。 EXECQUERY ステートメントの文法の詳細については、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を参照してください[SAP 内の EXECQUERY ステートメントに対して構文](../../adapters-and-accelerators/adapter-sap/syntax-for-an-execquery-statement-in-sap.md)です。  
  
 SQL Server Management Studio または Visual Studio での統合サービス プロジェクトから、SQL Server インポートのエクスポート ウィザードを開始することができます。 このセクションでは、Management Studio と Visual Studio の両方のインターフェイスから、ウィザードの実行について説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SQL Server Management Studio を使用して SAP データのインポート](../../adapters-and-accelerators/adapter-sap/import-sap-data-using-sql-server-management-studio.md)  
  
-   [Visual Studio を使用して SAP データのインポート](../../adapters-and-accelerators/adapter-sap/import-sap-data-using-visual-studio.md)  
  
## <a name="see-also"></a>参照  
 [使用して、.NET Framework Data Provider 用 mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)
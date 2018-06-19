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
# <a name="use-the-data-provider-for-siebel-with-ssis"></a>Siebel と SSIS のデータ プロバイダーを使用します。
使用することができます、 [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]) と共に SQL Server Integration Services (SSIS) Siebel システムから SQL Server データベース テーブルにデータをインポートする、フラット ファイル、またはその他の互換性のある変換先の型。 具体的には、このデータをインポートする実行可能な SSIS パッケージを作成することができます。  
  
 SQL Server データベースにデータをインポート、SQL Server インポートおよびエクスポート ウィザードを使用でき、SELECT クエリをインポートするデータを指定します。 サポートされているセマンティクスへのクエリを確認する必要があります、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]です。 クエリを SELECT の文法の詳細については、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]を参照してください[Siebel の SELECT ステートメントの構文](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md)です。  
  
> [!NOTE]
>  [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] SSIS で、EXEC ステートメントの使用をサポートしていません。  
  
 SQL Server Management Studio または Visual Studio での統合サービス プロジェクトから、SQL Server インポートおよびエクスポート ウィザードを開始することができます。 このセクションでは、SQL Server Management Studio および Visual Studio の両方のインターフェイスから、ウィザードの実行について説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Siebel を SQL Server Management Studio を使用してデータをインポートします。](../../adapters-and-accelerators/adapter-siebel/import-siebel-data-using-sql-server-management-studio.md)  
  
-   [Siebel を Visual Studio を使用してデータをインポートします。](../../adapters-and-accelerators/adapter-siebel/import-siebel-data-using-visual-studio.md)  
  
## <a name="see-also"></a>参照  
 [Siebel eBusiness Applications の .NET Framework データ プロバイダーを使用します。](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)
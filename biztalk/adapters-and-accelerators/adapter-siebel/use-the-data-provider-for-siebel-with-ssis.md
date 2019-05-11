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
# <a name="use-the-data-provider-for-siebel-with-ssis"></a>Siebel を SSIS と一緒に用データ プロバイダーを使用します。
使用することができます、 [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]) と共に SQL Server Integration Services (SSIS) Siebel システムから SQL Server データベース テーブルにデータをインポートする、フラット ファイル、またはその他の互換性のある変換先の型。 具体的には、このデータをインポートする実行可能な SSIS パッケージを作成できます。  
  
 SQL Server データベースにデータをインポート、SQL Server インポートおよびエクスポート ウィザードを使用してインポートするデータを指定する SELECT クエリを提供します。 サポートされているセマンティクスへのクエリを確認する必要があります、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]します。 クエリの SELECT、文法の詳細については、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]を参照してください[Siebel の SELECT ステートメントの構文](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md)します。  
  
> [!NOTE]
>  [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] EXEC ステートメント SSIS の使用をサポートしていません。  
  
 SQL Server インポートおよびエクスポート ウィザードは、SQL Server Management Studio または Visual Studio での統合サービス プロジェクトを開始できます。 このセクションでは、SQL Server Management Studio と Visual Studio の両方のインターフェイスから、ウィザードの実行について説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SQL Server Management Studio を使用して Siebel データをインポートする](../../adapters-and-accelerators/adapter-siebel/import-siebel-data-using-sql-server-management-studio.md)  
  
-   [Visual Studio を使用して Siebel データをインポートする](../../adapters-and-accelerators/adapter-siebel/import-siebel-data-using-visual-studio.md)  
  
## <a name="see-also"></a>参照  
 [.NET Framework Data Provider for Siebel eBusiness Applications を使用する](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)
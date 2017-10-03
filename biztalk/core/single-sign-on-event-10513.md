---
title: "シングル サインオン: イベント 10513 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3306223-111f-4abf-ae65-be839b355216
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f1be7ae463dbb1ee9651f69f231614cc11db5f1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10513"></a>シングル サインオン: イベント 10513
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10513|  
|イベント ソース|ENTSSO|  
|コンポーネント|N\A|  
|シンボル名|SSO_ERROR_DB_FIRST_ACCESS|  
|メッセージ テキスト|SSO データベースに接続に失敗しました: %1 %r<br /><br /> %2%r<br /><br /> エラー コード: %3|  
  
## <a name="explanation"></a>説明  
 このエラー イベントは、SSO サービスの開始時に SSO データベースに接続できないことを示します。 イベント メッセージには、指定された SQL Server 名とデータベース名を示すデータ ソース名 (DSN) 文字列、および SQL 接続ライブラリから返されたエラー メッセージが含まれます。  
  
 SSO サービスは、開始時に、レジストリで指定された SQL Server 名と SSO データベース名を使用して SSO データベースに接続しようとします。 SSO サービスは、接続が失敗するたびに 5 秒間待機しながら 12 回、合計で 1 分間、接続を試行します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、以下の 1 つ以上の操作を実行します。  
  
-   SQL Server (MSSQLSERVER) サービスが実行されていることを確認します。  
  
-   エラー メッセージに示されているデータ ソース名 (DSN) 文字列が正しく、適切な SQL Server 名とデータベース名が含まれていることを確認します。  
  
 詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   
  
-   [エンタープライズ シングル サインオンを実装します。](../core/implementing-enterprise-single-sign-on.md)  
  
-   [SSO データベース情報を表示する方法](../core/how-to-display-the-sso-database-information.md)  
  
-   [SSO を構成します。](../core/configuring-sso.md)  
  
-   SQL Server オンライン ブック
---
title: 'シングル サインオン: イベント 10514 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b527841-a2e2-44c7-a9cb-6e9a8eea2fba
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40077ead4157b4cc6c91a2c44b4a19569d76ebc1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270506"
---
# <a name="single-sign-on-event-10514"></a>シングル サインオン: イベント 10514
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10514|  
|イベント ソース|ENTSSO|  
|コンポーネント|N\A|  
|シンボル名|SSO_ERROR_DB_ACCESS|  
|メッセージ テキスト|SSO データベースへのアクセスを試みているときにエラーが発生しました。%r<br /><br /> 関数: %1 %r<br /><br /> ファイル: %2 %r<br /><br /> %3。%r<br /><br /> SQL エラー コード: %4 %r<br /><br /> エラー コード: %5|  
  
## <a name="explanation"></a>説明  
 このエラー イベントは、SSO データベースにアクセスしようとしたときに、SQL Server からエラーを受信したことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、以下の 1 つ以上の操作を実行します。  
  
-   SQL Server (MSSQLSERVER) サービスが実行されていることを確認します。  
  
-   イベントとエラー メッセージ センターを使用して SQL Server のエラー コードを確認して[http://go.microsoft.com/fwlink/?LinkID=20869](http://go.microsoft.com/fwlink/?LinkID=20869)です。  
  
 詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   
  
-   [エンタープライズ シングル サインオンを実装します。](../core/implementing-enterprise-single-sign-on.md)  
  
-   [SSO データベース情報を表示する方法](../core/how-to-display-the-sso-database-information.md)  
  
 SQL Server Books Online も参照してください。
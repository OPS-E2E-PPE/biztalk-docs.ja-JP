---
title: シングル サインオン:イベント 10514 |Microsoft Docs
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
ms.openlocfilehash: 8b3017f6a84910ecdfd0da07aeb0ae5c76485bc5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243441"
---
# <a name="single-sign-on-event-10514"></a>シングル サインオン:イベント 10514
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                    エンタープライズ シングル サインオン                                                                                     |
| 製品バージョン |                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                    |
|    イベント ID     |                                                                                              10514                                                                                               |
|  イベント ソース   |                                                                                              ENTSSO                                                                                              |
|    コンポーネント    |                                                                                               該当なし                                                                                                |
|  シンボル名  |                                                                                       SSO_ERROR_DB_ACCESS                                                                                        |
|  メッセージ テキスト   | SSO database.%r へのアクセスを試みているときにエラーが発生しました<br /><br /> 関数: %1 %r<br /><br /> ファイル: % 2 %r<br /><br /> %3.%r<br /><br /> SQL エラー コード: % 4 %r<br /><br /> エラー コード: %5 |
  
## <a name="explanation"></a>説明  
 このエラー イベントは、SSO データベースにアクセスする際にエラーが SQL Server から受信したことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、以下の 1 つ以上の操作を実行します。  
  
- SQL Server (MSSQLSERVER) サービスが実行されていることを確認します。  
  
- イベントとエラー メッセージ センターを使用して SQL Server エラー コードを確認して[ http://go.microsoft.com/fwlink/?LinkID=20869](http://go.microsoft.com/fwlink/?LinkID=20869)します。  
  
  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
- [Enterprise Single Sign-On の実装](../core/implementing-enterprise-single-sign-on.md)  
  
- [SSO データベース情報を表示する方法](../core/how-to-display-the-sso-database-information.md)  
  
  SQL Server オンライン ブックを参照してください。
---
title: シングル サインオン:イベント 10513 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b3306223-111f-4abf-ae65-be839b355216
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ec0cb1df806771e3676bcd580be2965498b618a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243399"
---
# <a name="single-sign-on-event-10513"></a>シングル サインオン:イベント 10513
## <a name="details"></a>詳細  

|                 |                                                                                      |
|-----------------|--------------------------------------------------------------------------------------|
|  製品名   |                              エンタープライズ シングル サインオン                               |
| 製品バージョン |              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]              |
|    イベント ID     |                                        10513                                         |
|  イベント ソース   |                                        ENTSSO                                        |
|    コンポーネント    |                                         該当なし                                          |
|  シンボル名  |                              SSO_ERROR_DB_FIRST_ACCESS                               |
|  メッセージ テキスト   | SSO データベースに接続に失敗しました: % 1 %r<br /><br /> % 2 %r<br /><br /> エラー コード: %3 |

## <a name="explanation"></a>説明  
 このエラー イベントは、開始するときに、SSO サービスが、SSO データベースに接続できないことを示します。 イベント メッセージには、SQL 接続ライブラリから返されたエラー メッセージと同様に、指定した SQL Server とデータベースの名前を示すデータ ソース名 (DSN) 文字列が含まれています。  

 SSO サービスの開始時に、レジストリで指定された SQL Server および SSO データベース名を使用して SSO データベースへの接続を試みます。 SSO サービスでは 12 回、接続を 5 秒間、合計で 1 分の各失敗した試行を待機しているがされます。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、以下の 1 つ以上の操作を実行します。  

- SQL Server (MSSQLSERVER) サービスが実行されていることを確認します。  

- エラー メッセージに示されているデータ ソース名 (DSN) 文字列が正しいと適切な SQL Server とデータベース名を確認します。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [Enterprise Single Sign-On の実装](../core/implementing-enterprise-single-sign-on.md)  

- [SSO データベース情報を表示する方法](../core/how-to-display-the-sso-database-information.md)  

- [SSO の構成](../core/configuring-sso.md)  

- SQL Server オンライン ブック

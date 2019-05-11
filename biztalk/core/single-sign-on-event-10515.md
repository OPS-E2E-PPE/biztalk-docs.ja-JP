---
title: シングル サインオン:イベント 10515 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41edc008-b6d3-401d-97af-80b36ab0ba55
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3071aa76f6a1366c3a17c38a51f81da7048331b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243446"
---
# <a name="single-sign-on-event-10515"></a>シングル サインオン:イベント 10515
## <a name="details"></a>詳細  
  
|                 |                                                                               |
|-----------------|-------------------------------------------------------------------------------|
|  製品名   |                           エンタープライズ シングル サインオン                           |
| 製品バージョン |          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]           |
|    イベント ID     |                                     10515                                     |
|  イベント ソース   |                                    ENTSSO                                     |
|    コンポーネント    |                                      該当なし                                      |
|  シンボル名  |                            SSO_ERROR_POLL_DATABASE                            |
|  メッセージ テキスト   | SSO データベースとの接続が切断されました。 SSO データベースが使用可能なことを確認します。 |
  
## <a name="explanation"></a>説明  
 このエラー イベントは、SSO サービスが SSO データベースとの接続を失ったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、以下の 1 つ以上の操作を実行します。  
  
- SQL Server (MSSQLSERVER) サービスが実行されていることを確認します。  
  
- リモート サーバー上にある場合は、SQL Server へのネットワーク接続を確認します。  
  
  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
- [Enterprise Single Sign-On の実装](../core/implementing-enterprise-single-sign-on.md)  
  
- [SSO データベース情報を表示する方法](../core/how-to-display-the-sso-database-information.md)  
  
- [SSO の構成](../core/configuring-sso.md)  
  
  SQL Server オンライン ブックも参照してください。
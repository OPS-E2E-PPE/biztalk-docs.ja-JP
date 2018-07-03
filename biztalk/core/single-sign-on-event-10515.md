---
title: 'シングル サインオン: イベント 10515 |Microsoft Docs'
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
ms.openlocfilehash: f1c3d7498bcd6a045936103d682d3643761a182c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980819"
---
# <a name="single-sign-on-event-10515"></a>シングル サインオン: イベント 10515
## <a name="details"></a>詳細  
  
|                 |                                                                               |
|-----------------|-------------------------------------------------------------------------------|
|  製品名   |                           エンタープライズ シングル サインオン                           |
| 製品バージョン |          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]           |
|    イベント ID     |                                     10515                                     |
|  イベント ソース   |                                    ENTSSO                                     |
|    コンポーネント    |                                      N\A                                      |
|  シンボル名  |                            SSO_ERROR_POLL_DATABASE                            |
|  メッセージ テキスト   | SSO データベースとの接続が切断されました。 SSO データベースが使用可能であることを確認してください。 |
  
## <a name="explanation"></a>説明  
 このエラー イベントは、SSO サービスと SSO データベースとの接続が切断されたことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、以下の 1 つ以上の操作を実行します。  
  
- SQL Server (MSSQLSERVER) サービスが実行されていることを確認します。  
  
- SQL Server がリモート サーバー上で実行されている場合は、ネットワーク接続を確認します。  
  
  詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   
  
- [Enterprise Single Sign-On の実装](../core/implementing-enterprise-single-sign-on.md)  
  
- [SSO データベース情報を表示する方法](../core/how-to-display-the-sso-database-information.md)  
  
- [SSO の構成](../core/configuring-sso.md)  
  
  SQL Server オンライン ブックも参照してください。
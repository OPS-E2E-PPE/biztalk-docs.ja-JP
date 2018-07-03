---
title: 'シングル サインオン: イベント 10522 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd634a57-01dc-44bd-bcf9-668689db7b77
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f8bb97c8c537cca8b2f9c6e9176409d7da4dd3e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972131"
---
# <a name="single-sign-on-event-10522"></a>シングル サインオン: イベント 10522
## <a name="details"></a>詳細  

|                 |                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------|
|  製品名   |                                   エンタープライズ シングル サインオン                                   |
| 製品バージョン |                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                   |
|    イベント ID     |                                             10522                                             |
|  イベント ソース   |                                            ENTSSO                                             |
|    コンポーネント    |                                              N\A                                              |
|  シンボル名  |                                      SSO_ERROR_REENCRYPT                                      |
|  メッセージ テキスト   | SSO データベースの再暗号化が失敗しました。 %1 分後に再試行されます。%r<br /><br /> エラー コード: %2 |

## <a name="explanation"></a>説明  
 このエラー イベントは、SSO データベースの再暗号化が失敗したことを示します。 SSO サービスは、マスター シークレット サーバーで開始すると、最初に、以前のマスター シークレットで暗号化されているものがまだ SSO データベースに存在するかどうかを調べます。 該当するものが見つかると、(以前のシークレットを使用して) その情報を暗号化解除し、現在のマスター シークレットを使用して再暗号化します。 何らかの理由でこの処理が失敗すると、このイベント メッセージが生成されます。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  

- エラー コードを調べて、エラーの根本原因を特定します。 ネットワークまたはデータベースの問題である可能性があります。 断続的なものである場合は、すぐに再暗号化が再び試みられるので、操作は必要ありません。 問題が断続的でない場合は、SSO サービスを停止し、問題の解決を試みます。 問題を解決したら SSO サービスを再起動します。SSO サービスを再起動すると、再暗号化が自動的に実行されます。  

  詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   

- [SSO データベース情報を表示する方法](../core/how-to-display-the-sso-database-information.md)  

- [マスター シークレット サーバー](../core/master-secret-server.md)

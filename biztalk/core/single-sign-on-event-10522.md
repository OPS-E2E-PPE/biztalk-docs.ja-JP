---
title: シングル サインオン:イベント 10522 |Microsoft Docs
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
ms.openlocfilehash: ac9347492793170faed39be91f2925e0ffdc1cdc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393019"
---
# <a name="single-sign-on-event-10522"></a>シングル サインオン:イベント 10522
## <a name="details"></a>詳細  

|                 |                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------|
|  製品名   |                                   エンタープライズ シングル サインオン                                   |
| 製品バージョン |                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                   |
|    イベント ID     |                                             10522                                             |
|  イベント ソース   |                                            ENTSSO                                             |
|    コンポーネント    |                                              該当なし                                              |
|  シンボル名  |                                      SSO_ERROR_REENCRYPT                                      |
|  メッセージ テキスト   | SSO データベースを再暗号化に失敗しました。 %1 minutes.%r にもう一度します。<br /><br /> エラー コード: %2 |

## <a name="explanation"></a>説明  
 このエラー イベントは、SSO データベースの再暗号化が失敗したことを示します。 マスタ シークレット サーバーで SSO サービスの起動時かどうかがありますが、SSO データベースを以前のマスター シークレットで暗号化されたままでを確認するは、まずことです。 ものが見つかると、(以前のシークレットを使用して) その情報を復号化し、現在のマスター シークレットを使用して再暗号化します。 何らかの理由でこの処理に失敗した場合は、このイベント メッセージが発行されます。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  

- エラーの根本原因の特定にエラー コードを確認します。 これは、ネットワークまたはデータベースの問題となる可能性があります。 断続的な場合は、し、アクションは必要ありませんので、短い遅延の後にもう一度再暗号化が試行されます。 問題が断続的でない場合は、SSO サービスを停止し、問題を解決しようとしてください。 問題が解決し、SSO サービスを再起動して、SSO サービスを再起動すると、再暗号化が実行自動的にします。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [SSO データベース情報を表示する方法](../core/how-to-display-the-sso-database-information.md)  

- [マスター シークレット サーバー](../core/master-secret-server.md)

---
title: 'シングル サインオン: イベント 10511 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 98371982-0db5-4ae0-9f92-f05a58e23b83
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 828dab394e773f99b31ca23f19b2816ab8558a10
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992091"
---
# <a name="single-sign-on-event-10511"></a>シングル サインオン: イベント 10511
## <a name="details"></a>詳細  

|                 |                                                                                                                                   |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                     エンタープライズ シングル サインオン                                                     |
| 製品バージョン |                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                     |
|    イベント ID     |                                                               10511                                                               |
|  イベント ソース   |                                                              ENTSSO                                                               |
|    コンポーネント    |                                                                N\A                                                                |
|  シンボル名  |                                                         SSO_ERROR_NO_DSN                                                          |
|  メッセージ テキスト   | SQL Server 名と SSO データベース名がレジストリ内に見つかりませんでした。 SSO 管理ツールを使用してこれらの値を構成してください。 |

## <a name="explanation"></a>説明  
 このエラー イベントは、SQL Server 名と SSO データベース名がレジストリ内に見つからなかったことを示します。 SSO サービスでは、SSO データベースに接続するためにこの情報が必要です。 この情報は、構成中にレジストリ内で設定されます。 このエラーは、構成が正常に完了していないか、または構成の完了後にレジストリ エントリが削除されたことを示している可能性があります。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、以下の 1 つ以上の操作を実行します。  

- 広い範囲での構成の失敗が疑われる場合は、製品の構成を解除し、構成プログラムを使用して再構成します。  

- この代わりに、これらの存在しない特定のレジストリ エントリを、SSO コマンド ライン ツール ssoconfig.exe を使用して設定することもできます。ssoconfig.exe は、SSO インストール ディレクトリ (通常、C:\Program Files\Common Files\Enterprise Single Sign-On) にあります。 SSO インストール ディレクトリが違う可能性があります。 使用して、 **-setdb**必要な SQL Server および SSO データベース名を設定するオプション。  

  詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   

- [Enterprise Single Sign-On の実装](../core/implementing-enterprise-single-sign-on.md)

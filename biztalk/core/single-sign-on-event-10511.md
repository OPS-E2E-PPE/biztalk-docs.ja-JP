---
title: シングル サインオン:イベント 10511 |Microsoft Docs
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
ms.openlocfilehash: 531e32a2c23c30095dc744c6e73d111ce9cccc13
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400249"
---
# <a name="single-sign-on-event-10511"></a>シングル サインオン:イベント 10511
## <a name="details"></a>詳細  

|                 |                                                                                                                                   |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                     エンタープライズ シングル サインオン                                                     |
| 製品バージョン |                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                     |
|    イベント ID     |                                                               10511                                                               |
|  イベント ソース   |                                                              ENTSSO                                                               |
|    コンポーネント    |                                                                該当なし                                                                |
|  シンボル名  |                                                         SSO_ERROR_NO_DSN                                                          |
|  メッセージ テキスト   | SQL Server および SSO データベース名がレジストリに見つかりませんでした。 SSO 管理ツールを使用すると、これらの値を構成できます。 |

## <a name="explanation"></a>説明  
 このエラー イベントは、SQL Server および SSO データベース名がレジストリ内に見つからなかったことを示します。 SSO サービスでは、SSO データベースに接続できるように、この情報が必要です。 この情報は、構成中に、レジストリに設定されます。 構成が正しく完了しませんでしたか、構成した後、レジストリ エントリが削除されたことが完了したこと可能性があります。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、以下の 1 つ以上の操作を実行します。  

- 多くの構成の失敗を疑いがある場合は、製品の構成を解除し、構成プログラムを使用してを再構成します。  

- またこれら特定の不足しているレジストリ エントリは、SSO コマンド ライン ツール ssoconfig.exe SSO インストール ディレクトリの通常 C:\Program files \common files \enterprise でシングル サインオンを使用して設定できます。 SSO インストール ディレクトリは、異なる場合があります。 使用して、 **-setdb**必要な SQL Server および SSO データベース名を設定するオプション。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [Enterprise Single Sign-On の実装](../core/implementing-enterprise-single-sign-on.md)

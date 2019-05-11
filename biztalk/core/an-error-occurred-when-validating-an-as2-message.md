---
title: AS2 メッセージを検証するときにエラーが発生しました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0cf97c63-2bff-4474-9cd8-f68634493dcc
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b7d797989290b0211e619e0c5ae4b4408cda02c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360065"
---
# <a name="an-error-occurred-when-validating-an-as2-message"></a>AS2 メッセージを検証するときにエラーが発生しました
## <a name="details"></a>詳細  

|                 |                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------|
|  製品名   |                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                   |
| 製品バージョン |                              [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                               |
|    イベント ID     |                                                           -                                                           |
|  イベント ソース   |                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                 |
|    コンポーネント    |                                                      AS2 エンジン                                                       |
|  シンボル名  |                                                           -                                                           |
|  メッセージ テキスト   | AS2 メッセージを検証するときにエラーが発生しました。 使用する証明書がないタイムアウトまたは失効を確認してください。 |

## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、AS2 受信パイプラインまたは AS2 送信パイプラインは AS2 メッセージを検証できなかったことを示します。 これは、署名の確認プロセスで使用される証明書が無効です、適切な場所には格納されませんまたは署名プロセスで使用される証明書と一致しない場合に発生することができます。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、以下の 1 つ以上の操作を実行します。  

- AS2 メッセージに署名ラッパーが有効であることを確認します。 ない場合は、エンコーダーによってメッセージを正しく署名された理由を判断します。  

- 署名プロセスで使用される秘密キーと署名の確認プロセスで使用される公開キーが一致することを確認します。  

- 署名および署名の検証に使用する証明書のキー使用法プロパティが 「データの暗号化」に設定されていることを確認します。  

- 中間証明機関のチェーンが切れていないことを確認します。 切れている場合は、古い証明書を削除し、新しい証明書を作成して使用します。  

- 証明書の有効期限を証明書ストアで調べて (証明書スナップインを含む MMC を使用)、証明書の有効期限が切れていないことを確認します。  

- 証明書失効リストを調べて、証明書が失効していないことを確認します。 (BizTalk Server が AS2 の全般プロパティで証明書失効リストのチェック プロパティをチェックして自動的に確認することが、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです)。  

- 署名の検証に使用される証明書がローカル コンピューターに格納されている/その他のユーザーとしてのストアの各 BizTalk server MIME/SMIME デコーダー パイプラインをホストする各ホスト インスタンス サービス アカウントのことを確認します。

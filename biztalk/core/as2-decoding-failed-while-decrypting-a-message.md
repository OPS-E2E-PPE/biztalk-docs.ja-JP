---
title: AS2 のデコード、メッセージの解読中に失敗しました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ab6f7ecd-23cf-4f6f-8f63-acc6618dc544
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78dea4d186de1b4cfe34998abc3f627eae0e8977
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528556"
---
# <a name="as2-decoding-failed-while-decrypting-a-message"></a>AS2 のデコード、メッセージの解読中に失敗しました
## <a name="details"></a>詳細  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       AS2 エンジン                                       |
|  シンボル名  |                                           -                                            |
|  メッセージ テキスト   |                    AS2 のデコードは、メッセージの解読中に失敗しました。                     |

## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、受信パイプラインの AS2 デコーダー コンポーネントが AS2 メッセージを解読できなかったことを意味します。 この問題は、解読のプロセスで使用された証明書が、有効でないか、適切な場所に置かれていないか、暗号化のプロセスで使用された証明書と一致していない場合に発生することがあります。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、以下の 1 つ以上の操作を実行します。  

- AS2 メッセージの暗号化ラッパーが有効であることを確認します。 原因がそれ以外である場合は、メッセージがエンコーダーによって正しくエンコードされなかった理由を特定します。  

- 暗号化のプロセスで使用された公開キーと、解読のプロセスで使用された秘密キーが一致しているかどうかを確認します。  

- 暗号化と解読に使用された証明書の "キー使用法" プロパティが "データの暗号化" に設定されていることを確認します。  

- 中間証明機関のチェーンが切れていないことを確認します。 切れている場合は、古い証明書を削除し、新しい証明書を作成して使用します。  

- 証明書の有効期限を証明書ストアで調べて (証明書スナップインを含む MMC を使用)、証明書の有効期限が切れていないことを確認します。  

- 証明書失効リストを調べて、証明書が失効していないことを確認します。 (BizTalk Server が AS2 の全般プロパティで証明書失効リストのチェック プロパティをチェックして自動的に確認することが、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです)。  

- 解読に使用された証明書が、各ホスト インスタンス サービス アカウントとして MIME/SMIME デコーダー パイプラインをホストする各 BizTalk サーバーの "現在のユーザー\個人用" ストアに保存されていることを確認します。

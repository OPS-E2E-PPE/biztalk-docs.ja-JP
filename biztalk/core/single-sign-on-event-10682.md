---
title: シングル サインオン:イベント 10682 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 46f0f425-3946-4bac-a412-488c4afe460d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1a78ed5dcb5897bfcab452285f5fb866fa12030
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397418"
---
# <a name="single-sign-on-event-10682"></a>シングル サインオン:イベント 10682
## <a name="details"></a>詳細  

|                 |                                                                                                |
|-----------------|------------------------------------------------------------------------------------------------|
|  製品名   |                                   エンタープライズ シングル サインオン                                    |
| 製品バージョン |                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                   |
|    イベント ID     |                                             10682                                              |
|  イベント ソース   |                                             ENTSSO                                             |
|    コンポーネント    |                                              該当なし                                               |
|  シンボル名  |                               SSO_WARN_REPLAY_INVALID_DIR_FOUND                                |
|  メッセージ テキスト   | ディレクトリが見つかった再生ファイルのディレクトリにされます。 ignored.%r<br />ディレクトリ: %1 |

## <a name="explanation"></a>説明  
 この警告イベントは、再生ファイルのディレクトリにディレクトリが見つかったことを示します。 再生ファイルは、ENTSSO サーバーが SSO データベースに接続できない場合、パスワード同期で使用されます。 ここで、パスワードの変更は一時的な暗号化ファイルに格納されも利用できなくなる、SSO データベースに再生されます。 再生ファイルのディレクトリは、再生ファイルのみを含める必要があります – ディレクトリが見つかった場合にこのエラー メッセージが発行されます。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の 1 つ以上の操作を行います。  

- コマンド ライン ツール ssoconfig-replayfiles を使用して、再生ディレクトリを変更します。  

- 使用中でない場合は、不適切なディレクトリを削除します。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [パスワード同期を構成する方法](../core/how-to-configure-password-synchronization.md)  

- [パスワード同期](../core/password-synchronization2.md)

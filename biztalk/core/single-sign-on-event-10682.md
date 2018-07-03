---
title: 'シングル サインオン: イベント 10682 |Microsoft Docs'
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
ms.openlocfilehash: 5c7ed830c44404e0365505b7dc0f3a5c6fec8a85
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999715"
---
# <a name="single-sign-on-event-10682"></a>シングル サインオン: イベント 10682
## <a name="details"></a>詳細  

|                 |                                                                                                |
|-----------------|------------------------------------------------------------------------------------------------|
|  製品名   |                                   エンタープライズ シングル サインオン                                    |
| 製品バージョン |                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                   |
|    イベント ID     |                                             10682                                              |
|  イベント ソース   |                                             ENTSSO                                             |
|    コンポーネント    |                                              N\A                                               |
|  シンボル名  |                               SSO_WARN_REPLAY_INVALID_DIR_FOUND                                |
|  メッセージ テキスト   | ディレクトリが見つかった再生ファイルのディレクトリにされます。 ignored.%r<br />ディレクトリ: %1 |

## <a name="explanation"></a>説明  
 この警告イベントは、再生ファイル ディレクトリ内でディレクトリが見つかったことを示します。 ENTSSO サーバーから SSO データベースに接続できない場合、パスワード同期で再生ファイルが使用されます。 ここで、パスワードの変更は一時的な暗号化ファイルに格納されも利用できなくなる、SSO データベースに再生されます。 再生ファイル ディレクトリは、再生ファイルのみを格納することが想定されています。このエラー メッセージは、ディレクトリが見つかった場合に発行されます。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解消するには、次の操作を行います:   

- コマンド ライン ツール ssoconfig -replayFiles を使用して、再生ディレクトリを変更します。  

- 使用中ではない場合は不適切なディレクトリを削除します。  

  詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   

- [パスワード同期を構成する方法](../core/how-to-configure-password-synchronization.md)  

- [パスワード同期](../core/password-synchronization2.md)

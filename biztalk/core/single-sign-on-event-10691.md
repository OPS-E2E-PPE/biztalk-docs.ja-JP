---
title: 'シングル サインオン: イベント 10691 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4fcefb49-c068-41e9-850d-99864c0899bf
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69acc99acd002f23d3d6e02430d58fb88f9651a3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009899"
---
# <a name="single-sign-on-event-10691"></a>シングル サインオン: イベント 10691
## <a name="details"></a>詳細  

|                 |                                                                                                             |
|-----------------|-------------------------------------------------------------------------------------------------------------|
|  製品名   |                                          エンタープライズ シングル サインオン                                          |
| 製品バージョン |                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                          |
|    イベント ID     |                                                    10691                                                    |
|  イベント ソース   |                                                   ENTSSO                                                    |
|    コンポーネント    |                                                     N\A                                                     |
|  シンボル名  |                                       SSO_ERROR_REPLAY_FILE_MISMATCH                                        |
|  メッセージ テキスト   | 再生ファイルに破損が検出されました。%r<br /><br /> 再生ファイル: % 1 %r<br /><br /> 追加データ: %2 |

## <a name="explanation"></a>説明  
 このエラー イベントは、SSO が SSO データベースとの接続を再び確立したが、対応する進行状況ファイルとの不一致が原因で再生ファイルを開けなかったことを示します。 SSO で再生ファイルを開くことができない場合、次の再生ファイルに進みます (次の再生ファイルがある場合)。  

 ENTSSO サーバーから SSO データベースに接続できない場合、パスワード同期で再生ファイルが使用されます。 進行ファイルでは、SSO データベースとの接続が再度失われた場合に SSO で再生ファイルをどこまで読み取ることができるかを示します。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  

- 関連するイベントについては、システムおよびアプリケーションのイベント ログを確認します。  

- 再生ファイルを削除します。  

  詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   

- [パスワード同期を構成する方法](../core/how-to-configure-password-synchronization.md)  

- [パスワード同期](../core/password-synchronization2.md)

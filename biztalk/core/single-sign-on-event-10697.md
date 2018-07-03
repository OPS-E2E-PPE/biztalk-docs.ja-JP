---
title: 'シングル サインオン: イベント 10697 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4263ecbd-939e-4374-b0b6-aada3b2af900
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 991d17351ddbaa998c0f7c90774e1615f3bc472e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980403"
---
# <a name="single-sign-on-event-10697"></a>シングル サインオン: イベント 10697
## <a name="details"></a>詳細  

|                 |                                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------|
|  製品名   |                                           エンタープライズ シングル サインオン                                           |
| 製品バージョン |                          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                           |
|    イベント ID     |                                                     10697                                                     |
|  イベント ソース   |                                                    ENTSSO                                                     |
|    コンポーネント    |                                                      N\A                                                      |
|  シンボル名  |                                       SSO_ERROR_PROGRESS_FILE_MISMATCH                                        |
|  メッセージ テキスト   | 進行ファイルで破損が検出されました。%r<br /><br /> 再生ファイル: % 1 %r<br /><br /> 追加データ: %2 |

## <a name="explanation"></a>説明  
 このエラー イベントは、SSO が SSO データベースとの接続を再び確立したが、対応する再生ファイルとの不一致が原因で進行状況ファイルを開けなかったことを示します。 進行ファイルを開くことができない場合は、最初の再生ファイルの先頭のレコードから開始されます。  

 ENTSSO サーバーから SSO データベースに接続できない場合、パスワード同期で再生ファイルが使用されます。 進行ファイルでは、SSO データベースとの接続が再度失われた場合に SSO で再生ファイルをどこまで読み取ることができるかを示します。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  

- 関連するイベントについては、システムおよびアプリケーションのイベント ログを確認します。  

  詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   

- [パスワード同期を構成する方法](../core/how-to-configure-password-synchronization.md)  

- [パスワード同期](../core/password-synchronization2.md)

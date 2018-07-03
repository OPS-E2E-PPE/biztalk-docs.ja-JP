---
title: 'シングル サインオン: イベント 10696 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4dff6d08-8a1f-4137-bda7-55271071da55
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3332a8104b96731a1fcf75267ec6fd69100c441a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968571"
---
# <a name="single-sign-on-event-10696"></a>シングル サインオン: イベント 10696
## <a name="details"></a>詳細  

|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  製品名   |                         エンタープライズ シングル サインオン                         |
| 製品バージョン |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    イベント ID     |                                   10696                                   |
|  イベント ソース   |                                  ENTSSO                                   |
|    コンポーネント    |                                    N\A                                    |
|  シンボル名  |                SSO_ERROR_PROGRESS_INCORRECT_RECORD_VERSION                |
|  メッセージ テキスト   | 進行ファイルで破損が検出されました。%r<br /><br /> ファイル名: %1 |

## <a name="explanation"></a>説明  
 このエラー イベントは、SSO が SSO データベースとの接続を再び確立したが、進行状況ファイルが破損しているために進行状況ファイルを読み取れなかったことを示します。 進行ファイルを開くことができない場合は、最初の再生ファイルの先頭のレコードから開始されます。  

 ENTSSO サーバーから SSO データベースに接続できない場合、パスワード同期で再生ファイルが使用されます。 進行ファイルでは、SSO データベースとの接続が再度失われた場合に SSO で再生ファイルをどこまで読み取ることができるかを示します。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  

- 関連するイベントについては、システムおよびアプリケーションのイベント ログを確認します。  

  詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   

- [パスワード同期を構成する方法](../core/how-to-configure-password-synchronization.md)  

- [パスワード同期](../core/password-synchronization2.md)

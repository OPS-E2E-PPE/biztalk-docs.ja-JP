---
title: 'シングル サインオン: イベント 10685 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 810b37b5-51c4-4201-8d88-0bf7d9e16dae
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b276432363f6073627aaa9033c2b78b730ccda1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992523"
---
# <a name="single-sign-on-event-10685"></a>シングル サインオン: イベント 10685
## <a name="details"></a>詳細  

|                 |                                                                                                      |
|-----------------|------------------------------------------------------------------------------------------------------|
|  製品名   |                                      エンタープライズ シングル サインオン                                       |
| 製品バージョン |                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                      |
|    イベント ID     |                                                10685                                                 |
|  イベント ソース   |                                                ENTSSO                                                |
|    コンポーネント    |                                                 N\A                                                  |
|  シンボル名  |                                     SSO_WARN_REPLAY_CANNOT_OPEN                                      |
|  メッセージ テキスト   | 再生ファイルまたは進行状況ファイルを開けませんでした。%r<br /><br /> ファイル名: %1 %r<br /><br /> エラー コード: %2 |

## <a name="explanation"></a>説明  
 この警告イベントは、SSO が SSO データベースとの接続を再び確立したが、再生ファイルまたは進行状況ファイルを開くことができなかったことを示します。 SSO で再生ファイルを開くことができなかった場合、次の再生ファイルが処理されます。  

 ENTSSO サーバーから SSO データベースに接続できない場合、パスワード同期で再生ファイルが使用されます。 進行状況ファイルは、SSO データベースとの接続が再び切断された場合に、部分的に再生ファイルを再生することによって、どの程度 SSO を通じて再生ファイルを読み取ることができたかを示します。  

## <a name="user-action"></a>ユーザーの操作  
 この警告イベントを解決するには、次の手順を実行します。  

- システムおよびアプリケーションのイベント ログで関連するイベントを確認し、SSO が SSO データベースに接続できなかった理由を特定します。  

  詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   

- [パスワード同期を構成する方法](../core/how-to-configure-password-synchronization.md)  

- [パスワード同期](../core/password-synchronization2.md)

---
title: シングル サインオン:イベント 10693 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 672bac7d-0ccc-4a42-a49d-57e387f4cf3a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6cef53efa210d38d145dd4859fd3363e853a71fe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397361"
---
# <a name="single-sign-on-event-10693"></a>シングル サインオン:イベント 10693
## <a name="details"></a>詳細  

|                 |                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------|
|  製品名   |                                       エンタープライズ シングル サインオン                                        |
| 製品バージョン |                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                       |
|    イベント ID     |                                                 10693                                                  |
|  イベント ソース   |                                                 ENTSSO                                                 |
|    コンポーネント    |                                                  該当なし                                                   |
|  シンボル名  |                                    SSO_WARNING_REPLAY_CANNOT_CREATE                                    |
|  メッセージ テキスト   | 再生を作成または進行状況の file.%r できませんでした。<br /><br /> ファイル名: %1 %r<br /><br /> エラー コード: %2 |

## <a name="explanation"></a>説明  
 この警告イベントは、SSO が SSO データベースへの接続が失われたときに再生や進行状況ファイルを作成できなかったことを示します。  

 再生ファイルは、ENTSSO サーバーが SSO データベースに接続できない場合、パスワード同期で使用されます。 進行状況ファイルがどこまで方法を示します SSO が SSO データベースと再生ファイルのケースで連絡先が再度失われたを読めるようにします。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  

- システムおよびアプリケーションのイベント ログで関連するイベントを確認します。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [パスワード同期を構成する方法](../core/how-to-configure-password-synchronization.md)  

- [パスワード同期](../core/password-synchronization2.md)

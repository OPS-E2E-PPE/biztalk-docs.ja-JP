---
title: シングル サインオン:イベント 10727 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ff7ac94-6f1e-4e56-853e-efc50b1fa1b6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4a6dcf108030a1679601e7c7a39a0f09b13d81a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65259014"
---
# <a name="single-sign-on-event-10727"></a>シングル サインオン:イベント 10727
## <a name="details"></a>詳細  

|                 |                                                                                                                                          |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                        エンタープライズ シングル サインオン                                                         |
| 製品バージョン |                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                        |
|    イベント ID     |                                                                  10727                                                                   |
|  イベント ソース   |                                                                  ENTSSO                                                                  |
|    コンポーネント    |                                                                   該当なし                                                                    |
|  シンボル名  |                                                      SSO_WARN_REPLAY_RECORD_FAILED                                                       |
|  メッセージ テキスト   | 再生の保存された外部パスワード変更 failed.%r<br /><br /> アダプター: % 1 %r<br /><br /> ファイル名: % 2 %r<br /><br /> エラー コード: %3 |

## <a name="explanation"></a>説明  
 この警告は、SSO が再生ファイルに記録されたパスワードの変更を再生することを示します。  

 再生ファイルは、ENTSSO サーバーが SSO データベースに接続できない場合、パスワード同期で使用されます。 進行状況ファイルがどこまで方法を示します SSO が SSO データベースと再生ファイルのケースで連絡先が再度失われたを読めるようにします。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います。  

- システムおよびアプリケーションのイベント ログで関連するイベントを確認します。  

  詳細については、次のリソースを参照してください。  

- [パスワード同期を構成する方法](../core/how-to-configure-password-synchronization.md)  

- [パスワード同期](../core/password-synchronization2.md)

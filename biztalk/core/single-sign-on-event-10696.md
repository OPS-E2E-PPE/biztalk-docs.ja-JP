---
title: シングル サインオン:イベント 10696 |Microsoft Docs
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
ms.openlocfilehash: 364abc55edf749a01828b5188a0ba55ad2a151b4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397327"
---
# <a name="single-sign-on-event-10696"></a>シングル サインオン:イベント 10696
## <a name="details"></a>詳細  

|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  製品名   |                         エンタープライズ シングル サインオン                         |
| 製品バージョン |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    イベント ID     |                                   10696                                   |
|  イベント ソース   |                                  ENTSSO                                   |
|    コンポーネント    |                                    該当なし                                    |
|  シンボル名  |                SSO_ERROR_PROGRESS_INCORRECT_RECORD_VERSION                |
|  メッセージ テキスト   | 進行状況 file.%r で破損が検出されました<br /><br /> ファイル名: %1 |

## <a name="explanation"></a>説明  
 このエラー イベントは、SSO が SSO データベースとの接続が再び確立したが、破損のため、進行状況ファイルを読み取ることができなかったことを示します。 SSO では、進行状況ファイルを開くことはできません場合、が、最初の再生ファイルの先頭のレコードから開始されます。  

 再生ファイルは、ENTSSO サーバーが SSO データベースに接続できない場合、パスワード同期で使用されます。 進行状況ファイルがどこまで方法を示します SSO が SSO データベースと再生ファイルのケースで連絡先が再度失われたを読めるようにします。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  

- システムおよびアプリケーションのイベント ログで関連するイベントを確認します。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [パスワード同期を構成する方法](../core/how-to-configure-password-synchronization.md)  

- [パスワード同期](../core/password-synchronization2.md)

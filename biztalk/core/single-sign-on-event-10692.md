---
title: シングル サインオン:イベント 10692 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 78a476ca-32eb-4f37-a807-25850503db6e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fdfd3359baec8f4dbecaaafc6acd0e614956ffcc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397351"
---
# <a name="single-sign-on-event-10692"></a>シングル サインオン:イベント 10692
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                      エンタープライズ シングル サインオン                                                                                                                      |
| 製品バージョン |                                                                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                      |
|    イベント ID     |                                                                                                                                10692                                                                                                                                |
|  イベント ソース   |                                                                                                                               ENTSSO                                                                                                                                |
|    コンポーネント    |                                                                                                                                 該当なし                                                                                                                                 |
|  シンボル名  |                                                                                                                    SSO_WARN_REPLAY_ACCESS_DENIED                                                                                                                    |
|  メッセージ テキスト   | 最初の呼び出し元が adapter.%r アクセス アカウントのメンバーではなくなったために、外部パスワード変更を再生することはできません。<br /><br /> 再生ファイル: % 1 %r<br /><br /> アダプター: % 2 %r<br /><br /> 最初の呼び出し元: % 3 %r<br /><br /> アクセス アカウント: %4 |

## <a name="explanation"></a>説明  
 この警告イベントは、こと SSO が SSO データベースとの接続を再確立が (SSO データベース) に変更を加えることができません指定再生ファイルで、変更を最初に指定されたアカウントが有効ではなくなったためにを示します。  

 再生ファイルは、ENTSSO サーバーが SSO データベースに接続できない場合、パスワード同期で使用されます。 進行状況ファイルがどこまで方法を示します SSO が SSO データベースと再生ファイルのケースで連絡先が再度失われたを読めるようにします。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います。  

- システムおよびアプリケーションのイベント ログで関連するイベントを確認します。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [パスワード同期を構成する方法](../core/how-to-configure-password-synchronization.md)  

- [パスワード同期](../core/password-synchronization2.md)

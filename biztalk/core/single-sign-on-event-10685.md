---
title: シングル サインオン:イベント 10685 |Microsoft Docs
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
ms.openlocfilehash: f73b44e334c60a59211b59a46f5c9a2dacffa8ed
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397397"
---
# <a name="single-sign-on-event-10685"></a>シングル サインオン:イベント 10685
## <a name="details"></a>詳細  

|                 |                                                                                                      |
|-----------------|------------------------------------------------------------------------------------------------------|
|  製品名   |                                      エンタープライズ シングル サインオン                                       |
| 製品バージョン |                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                      |
|    イベント ID     |                                                10685                                                 |
|  イベント ソース   |                                                ENTSSO                                                |
|    コンポーネント    |                                                 該当なし                                                  |
|  シンボル名  |                                     SSO_WARN_REPLAY_CANNOT_OPEN                                      |
|  メッセージ テキスト   | 再生を開くまたは file.%r 進行状況できませんでした。<br /><br /> ファイル名: %1 %r<br /><br /> エラー コード: %2 |

## <a name="explanation"></a>説明  
 この警告イベントは、SSO が SSO データベースとの接続が再び確立したが、再生ファイルまたは進行状況ファイルを開くことができなかったことを示します。 SSO で再生ファイルを開くことはできない場合は、これは次の再生ファイルに進みます。  

 再生ファイルは、ENTSSO サーバーが SSO データベースに接続できない場合、パスワード同期で使用されます。 進行状況ファイルは、どの程度 SSO を通じて再生ファイルのケースで連絡先 SSO データベースとが読めるように失われたもう一度再生ファイルの再生段階を示します。  

## <a name="user-action"></a>ユーザーの操作  
 この警告イベントを解決するには、次の操作を行います。  

- SSO が SSO データベースに接続できない理由を確認する関連するイベントのシステムおよびアプリケーション イベント ログを確認する必要があります。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [パスワード同期を構成する方法](../core/how-to-configure-password-synchronization.md)  

- [パスワード同期](../core/password-synchronization2.md)

---
title: シングル サインオン:イベント 10698 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f467934d-fef5-4962-a341-18f272d84108
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd2f52e4cabfac6309e33c3598921dc6001f006c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397300"
---
# <a name="single-sign-on-event-10698"></a>シングル サインオン:イベント 10698
## <a name="details"></a>詳細  

|                 |                                                                      |
|-----------------|----------------------------------------------------------------------|
|  製品名   |                      エンタープライズ シングル サインオン                       |
| 製品バージョン |      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]      |
|    イベント ID     |                                10698                                 |
|  イベント ソース   |                                ENTSSO                                |
|    コンポーネント    |                                 該当なし                                  |
|  シンボル名  |                     SSO_INFO_REPLAY_FILE_DELETED                     |
|  メッセージ テキスト   | 再生または進行状況ファイルが deleted.%r<br /><br /> ファイル名: %1 |

## <a name="explanation"></a>説明  
 この情報イベントは、SSO が再生または進行ファイルを削除することを示します。  

 再生ファイルは、ENTSSO サーバーが SSO データベースに接続できない場合、パスワード同期で使用されます。 進行状況ファイルがどこまで方法を示します SSO が SSO データベースと再生ファイルのケースで連絡先が再度失われたを読めるようにします。  

## <a name="user-action"></a>ユーザーの操作  

- ユーザー操作は必要ありません。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [パスワード同期を構成する方法](../core/how-to-configure-password-synchronization.md)  

- [パスワード同期](../core/password-synchronization2.md)

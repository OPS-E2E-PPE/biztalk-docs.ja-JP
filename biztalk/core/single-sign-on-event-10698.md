---
title: 'シングル サインオン: イベント 10698 |Microsoft Docs'
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
ms.openlocfilehash: aacd272480ddb58de38960ae8dc1a744815ced64
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966475"
---
# <a name="single-sign-on-event-10698"></a>シングル サインオン: イベント 10698
## <a name="details"></a>詳細  

|                 |                                                                      |
|-----------------|----------------------------------------------------------------------|
|  製品名   |                      エンタープライズ シングル サインオン                       |
| 製品バージョン |      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]      |
|    イベント ID     |                                10698                                 |
|  イベント ソース   |                                ENTSSO                                |
|    コンポーネント    |                                 N\A                                  |
|  シンボル名  |                     SSO_INFO_REPLAY_FILE_DELETED                     |
|  メッセージ テキスト   | 再生ファイルまたは進行状況ファイルが削除されました。%r<br /><br /> ファイル名: %1 |

## <a name="explanation"></a>説明  
 この情報イベントは、SSO が再生ファイルまたは進行状況ファイルを削除したことを示します。  

 ENTSSO サーバーから SSO データベースに接続できない場合、パスワード同期で再生ファイルが使用されます。 進行ファイルでは、SSO データベースとの接続が再度失われた場合に SSO で再生ファイルをどこまで読み取ることができるかを示します。  

## <a name="user-action"></a>ユーザーの操作  

- ユーザーの操作は必要ありません。  

  詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   

- [パスワード同期を構成する方法](../core/how-to-configure-password-synchronization.md)  

- [パスワード同期](../core/password-synchronization2.md)

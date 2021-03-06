---
title: シングル サインオン:イベント 10699 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cff26533-e4d7-47b5-92d5-bd8c72fab89a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2cd62c4d952b9375b5d9255efc2f46add36dbb5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397297"
---
# <a name="single-sign-on-event-10699"></a>シングル サインオン:イベント 10699
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                       エンタープライズ シングル サインオン                                                                                                       |
| 製品バージョン |                                                                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                       |
|    イベント ID     |                                                                                                                 10699                                                                                                                 |
|  イベント ソース   |                                                                                                                ENTSSO                                                                                                                 |
|    コンポーネント    |                                                                                                                  該当なし                                                                                                                  |
|  シンボル名  |                                                                                           SSO_INFO_EXTERNAL_PASSWORD_CHANGE_RECEIVED_REPLAY                                                                                           |
|  メッセージ テキスト   | (再生 file).%r からアダプターから外部パスワード変更を受け取りました<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: % 2 %r<br /><br /> 外部アカウント: % 3 %r<br /><br /> クライアント ユーザー: % 4 %r<br /><br /> レコード数: %5 |

## <a name="explanation"></a>説明  
 この情報イベントは、再生ファイルに記録されたアダプターから外部パスワード変更を受け取ったことを示します。 SSO が再生ファイルから保存された外部パスワード変更を再生しています。  

 再生ファイルは、ENTSSO サーバーが SSO データベースに接続できない場合、パスワード同期で使用されます。 進行状況ファイルがどこまで方法を示します SSO が SSO データベースと再生ファイルのケースで連絡先が再度失われたを読めるようにします。  

## <a name="user-action"></a>ユーザーの操作  

- ユーザー操作は必要ありません。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [パスワード同期を構成する方法](../core/how-to-configure-password-synchronization.md)  

- [パスワード同期](../core/password-synchronization2.md)

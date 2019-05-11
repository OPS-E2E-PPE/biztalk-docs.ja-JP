---
title: シングル サインオン:イベント 10687 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10b3fe2c-a7ba-47e1-a753-4eaa64b01a60
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77412a149c79e508c03b245cba04a76c87542936
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397390"
---
# <a name="single-sign-on-event-10687"></a>シングル サインオン:イベント 10687
## <a name="details"></a>詳細  

|                 |                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                               エンタープライズ シングル サインオン                                               |
| 製品バージョン |                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                               |
|    イベント ID     |                                                         10687                                                         |
|  イベント ソース   |                                                        ENTSSO                                                         |
|    コンポーネント    |                                                          該当なし                                                          |
|  シンボル名  |                                               SSO_INFO_REPLAY_COMPLETE                                                |
|  メッセージ テキスト   | 再生の保存された外部パスワード変更 completed.%r<br /><br /> 再生ファイル: % 1 %r<br /><br /> 追加データ: %2 |

## <a name="explanation"></a>説明  
 この情報イベントは、SSO の保存された外部パスワード変更ファイルの再生が完了したことを示します。 再生ファイルは、ENTSSO サーバーが SSO データベースに接続できない場合、パスワード同期で使用されます。  

## <a name="user-action"></a>ユーザーの操作  

- ユーザー操作は必要ありません。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [パスワード同期を構成する方法](../core/how-to-configure-password-synchronization.md)  

- [パスワード同期](../core/password-synchronization2.md)

---
title: シングル サインオン:イベント 10741 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58b6b093-d136-498f-a3b5-c413150da956
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2150f33b90137d5f5e1258a829901426a45d7856
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291734"
---
# <a name="single-sign-on-event-10741"></a>シングル サインオン:イベント 10741
## <a name="details"></a>詳細  

|                 |                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------|
|  製品名   |                                 エンタープライズ シングル サインオン                                 |
| 製品バージョン |                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                 |
|    イベント ID     |                                           10741                                           |
|  イベント ソース   |                                          ENTSSO                                           |
|    コンポーネント    |                                            該当なし                                            |
|  シンボル名  |                                SSO_WARN_SAVING_REPLAY_FILE                                |
|  メッセージ テキスト   | 再生または進行状況の file.%r を保存しています<br /><br /> 保存したファイル: % 1 %r<br /><br /> エラー コード: %2 |

## <a name="explanation"></a>説明  
 この警告イベントは、SSO が再生または進行ファイルを保存することを示します。  

 再生ファイルは、ENTSSO サーバーが SSO データベースに接続できない場合、パスワード同期で使用されます。 進行状況ファイルがどこまで方法を示します SSO が SSO データベースと再生ファイルのケースで連絡先が再度失われたを読めるようにします。  

## <a name="user-action"></a>ユーザーの操作  

- ユーザー操作は必要ありません。  

  詳細については、次のリソースを参照してください。  

- [パスワード同期](../core/password-synchronization2.md)

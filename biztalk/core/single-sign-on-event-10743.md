---
title: シングル サインオン:イベント 10743 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2908bc9-1fac-4ab9-869f-0c5512864da4
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10ec09fac8f7b555cb189e032b94bf0c8f8da839
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65278026"
---
# <a name="single-sign-on-event-10743"></a>シングル サインオン:イベント 10743
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                   エンタープライズ シングル サインオン                                                                    |
| 製品バージョン |                                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                   |
|    イベント ID     |                                                                             10743                                                                              |
|  イベント ソース   |                                                                             ENTSSO                                                                             |
|    コンポーネント    |                                                                              該当なし                                                                               |
|  シンボル名  |                                                                    SSO_ERROR_REPLAY_STOPPED                                                                    |
|  メッセージ テキスト   | Errors.%r により保存された外部パスワード変更の再生が停止しました<br /><br /> 再生ファイル: % 1 %r<br /><br /> 追加データ: % 2 %r<br /><br /> エラー コード: %3 |

## <a name="explanation"></a>説明  
 イベントは、その再生を示します。 このエラーには、エラーのために停止する外部パスワード変更が保存されます。  

 再生ファイルは、ENTSSO サーバーが SSO データベースに接続できない場合、パスワード同期で使用されます。 進行状況ファイルがどこまで方法を示します SSO が SSO データベースと再生ファイルのケースで連絡先が再度失われたを読めるようにします。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  

- システムおよびアプリケーションのイベント ログで関連するイベントを確認します。  

  詳細については、次のリソースを参照してください。  

- [パスワード同期を構成する方法](../core/how-to-configure-password-synchronization.md)  

- [パスワード同期](../core/password-synchronization2.md)

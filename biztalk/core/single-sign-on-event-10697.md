---
title: シングル サインオン:イベント 10697 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4263ecbd-939e-4374-b0b6-aada3b2af900
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f18e8ba525f742226f2f38efd285dd58f6896e24
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397310"
---
# <a name="single-sign-on-event-10697"></a>シングル サインオン:イベント 10697
## <a name="details"></a>詳細  

|                 |                                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------|
|  製品名   |                                           エンタープライズ シングル サインオン                                           |
| 製品バージョン |                          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                           |
|    イベント ID     |                                                     10697                                                     |
|  イベント ソース   |                                                    ENTSSO                                                     |
|    コンポーネント    |                                                      該当なし                                                      |
|  シンボル名  |                                       SSO_ERROR_PROGRESS_FILE_MISMATCH                                        |
|  メッセージ テキスト   | 進行状況 file.%r で破損が検出されました<br /><br /> 再生ファイル: % 1 %r<br /><br /> 追加データ: %2 |

## <a name="explanation"></a>説明  
 このエラー イベントは、SSO が SSO データベースとの接続が再び確立したが、対応する再生ファイルとの不一致により進行状況ファイルを開くことができなかったことを示します。 SSO では、進行状況ファイルを開くことはできません場合、が、最初の再生ファイルの先頭のレコードから開始されます。  

 再生ファイルは、ENTSSO サーバーが SSO データベースに接続できない場合、パスワード同期で使用されます。 進行状況ファイルがどこまで方法を示します SSO が SSO データベースと再生ファイルのケースで連絡先が再度失われたを読めるようにします。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  

- システムおよびアプリケーションのイベント ログで関連するイベントを確認します。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [パスワード同期を構成する方法](../core/how-to-configure-password-synchronization.md)  

- [パスワード同期](../core/password-synchronization2.md)

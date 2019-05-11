---
title: シングル サインオン:イベント 10726 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 12fbac2d-30ca-4f4c-989b-d770b0f623d9
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c14aea83bef1213eeda4bf56e4de7e400ee3e56
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258979"
---
# <a name="single-sign-on-event-10726"></a>シングル サインオン:イベント 10726
## <a name="details"></a>詳細  

|                 |                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                             エンタープライズ シングル サインオン                                                              |
| 製品バージョン |                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                             |
|    イベント ID     |                                                                       10726                                                                        |
|  イベント ソース   |                                                                       ENTSSO                                                                       |
|    コンポーネント    |                                                                        該当なし                                                                         |
|  シンボル名  |                                                            SSO_ERROR_REPLAY_CORRUPTION                                                             |
|  メッセージ テキスト   | 再生または進行状況 file.%r で破損が検出されました<br /><br /> ファイル名: %1 %r<br /><br /> 追加データ: % 2 %r<br /><br /> エラー コード: %3 |

## <a name="explanation"></a>説明  
 このエラー イベントは、SSO が SSO データベースとの接続が再び確立したが、破損のため、再生ファイルを読み取ることができなかったことを示します。 SSO で再生ファイルを開くことはできない場合は、(存在する場合)、[次へ] の再生ファイルに進みます。  

 再生ファイルは、ENTSSO サーバーが SSO データベースに接続できない場合、パスワード同期で使用されます。 進行状況ファイルがどこまで方法を示します SSO が SSO データベースと再生ファイルのケースで連絡先が再度失われたを読めるようにします。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  

- システムおよびアプリケーションのイベント ログで関連するイベントを確認します。  

- 再生ファイルを削除します。  

  詳細については、次のリソースを参照してください。  

- [パスワード同期を構成する方法](../core/how-to-configure-password-synchronization.md)  

- [パスワード同期](../core/password-synchronization2.md)

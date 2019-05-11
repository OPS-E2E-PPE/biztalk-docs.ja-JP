---
title: シングル サインオン:イベント 10717 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14691e0f-a399-4b4d-9dd5-516bf8d3a167
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c47ff4ceb707d1cbd353f88c9335d226a9a0158d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397166"
---
# <a name="single-sign-on-event-10717"></a>シングル サインオン:イベント 10717
## <a name="details"></a>詳細  

|                 |                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                            エンタープライズ シングル サインオン                                                             |
| 製品バージョン |                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                            |
|    イベント ID     |                                                                      10717                                                                       |
|  イベント ソース   |                                                                      ENTSSO                                                                      |
|    コンポーネント    |                                                                       該当なし                                                                        |
|  シンボル名  |                                                         SSO_ERROR_NEW_REPLAY_DIR_FAILED                                                          |
|  メッセージ テキスト   | 再生ファイルの directory.%r を作成できませんでした。<br /><br /> クライアント ユーザー: 1 %r<br /><br /> 再生ファイル ディレクトリ: % 2 %r<br /><br /> エラー コード: %3 |

## <a name="explanation"></a>説明  
 このエラー イベントは、再生ファイルのディレクトリが作成しないことを示します。  

 パスワード同期アダプターから SSO サービスで、パスワードの変更を受信したときに、SSO データベースに格納されます。 SSO データベースが一時的に利用できない場合、パスワードの変更が再生ファイルにローカルに格納されます。 再生ファイルは、再生ファイルのディレクトリに格納されます。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  

- 再生ファイル ディレクトリが表示され、1 つのチェックでは存在しない、SSO サービスと同じサービス アカウントを使用して手動で作成しようとしません。 SSO サービスと同じアカウントを使用して、再生ファイル ディレクトリを作成できない場合は、そのアカウントのアクセス許可を確認します。  

  詳細については、次のリソースを参照してください。  

- [パスワード同期を構成する方法](../core/how-to-configure-password-synchronization.md)  

- [パスワード同期](../core/password-synchronization2.md)

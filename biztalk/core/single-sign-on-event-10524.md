---
title: シングル サインオン:イベント 10524 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55e26da3-f67f-4f87-92e5-2f8765b19989
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d135f8856707527eb3368b579b6f77d541cbb84b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262551"
---
# <a name="single-sign-on-event-10524"></a>シングル サインオン:イベント 10524
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                  エンタープライズ シングル サインオン                                                                                  |
| 製品バージョン |                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                  |
|    イベント ID     |                                                                                            10524                                                                                            |
|  イベント ソース   |                                                                                           ENTSSO                                                                                            |
|    コンポーネント    |                                                                                             該当なし                                                                                             |
|  シンボル名  |                                                                               SSO_ERROR_RESTORE_SECRET_FAILED                                                                               |
|  メッセージ テキスト   | マスター secrets.%r の復元に失敗しました<br /><br /> ファイル名: %1 %r<br /><br /> 現在の MSID: % 2 %r<br /><br /> 以前の MSID: % 3 %r<br /><br /> クライアント ユーザー: % 4 %r<br /><br /> エラー コード: %5 |

## <a name="explanation"></a>説明  
 このエラー イベントは、バックアップ ファイルからマスター シークレットを復元するユーザーの試行が失敗したことを示します。 原因としては、アクセス許可 (マスター シークレットを復元するのには、SSO 管理者である必要があります) の問題またはバックアップ ファイルのファイルの破損原因として考えられます。 このような場合があります関連するメッセージ、アプリケーション イベント ログ。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、以下の 1 つ以上の操作を実行します。  

- アプリケーション イベント ログの関連するイベントまたはエラーを確認します。  

- 適切な SSO 管理者のアクセス許可があることを確認します。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [マスター シークレットを復元する方法](../core/how-to-restore-the-master-secret.md)  

- [マスター シークレットをバックアップする方法](../core/how-to-back-up-the-master-secret.md)  

- [マスター シークレットを生成する方法](../core/how-to-generate-the-master-secret.md)

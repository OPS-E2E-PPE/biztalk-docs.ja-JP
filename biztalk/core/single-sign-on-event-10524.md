---
title: 'シングル サインオン: イベント 10524 |Microsoft Docs'
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
ms.openlocfilehash: 3f873dab5d4d5f00897e498e2bb88b6ae9a2f040
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009507"
---
# <a name="single-sign-on-event-10524"></a>シングル サインオン: イベント 10524
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                  エンタープライズ シングル サインオン                                                                                  |
| 製品バージョン |                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                  |
|    イベント ID     |                                                                                            10524                                                                                            |
|  イベント ソース   |                                                                                           ENTSSO                                                                                            |
|    コンポーネント    |                                                                                             N\A                                                                                             |
|  シンボル名  |                                                                               SSO_ERROR_RESTORE_SECRET_FAILED                                                                               |
|  メッセージ テキスト   | マスター シークレットを復元できませんでした。%r<br /><br /> ファイル名: %1 %r<br /><br /> 現在の MSID: % 2 %r<br /><br /> 以前の MSID: % 3 %r<br /><br /> クライアント ユーザー: % 4 %r<br /><br /> エラー コード: %5 |

## <a name="explanation"></a>説明  
 このエラー イベントは、ユーザーがバックアップ ファイルからマスター シークレットを復元しようとしたが、失敗したことを示します。 原因としては、アクセス許可 (マスター シークレットを復元するのには、SSO 管理者である必要があります) の問題またはバックアップ ファイルのファイルの破損原因として考えられます。 これらの場合、アプリケーション イベント ログに関連するメッセージがあります。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、以下の 1 つ以上の操作を実行します。  

- 関連するイベントまたはエラーについては、アプリケーション イベント ログを確認します。  

- 適切な SSO 管理者のアクセス許可があることを確認します。  

  詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   

- [マスター シークレットを復元する方法](../core/how-to-restore-the-master-secret.md)  

- [マスター シークレットをバックアップする方法](../core/how-to-back-up-the-master-secret.md)  

- [マスター シークレットを生成する方法](../core/how-to-generate-the-master-secret.md)

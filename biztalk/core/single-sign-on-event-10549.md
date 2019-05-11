---
title: シングル サインオン:イベント 10549 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a18eb63-700c-4f49-acc4-890abe2a00ff
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac97f659dfc1f3b152df36c136fc45c3ef4238d8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243379"
---
# <a name="single-sign-on-event-10549"></a>シングル サインオン:イベント 10549
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                          |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                エンタープライズ シングル サインオン                                                                                 |
| 製品バージョン |                                                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                |
|    イベント ID     |                                                                                          10549                                                                                           |
|  イベント ソース   |                                                                                          ENTSSO                                                                                          |
|    コンポーネント    |                                                                                            CO                                                                                            |
|  シンボル名  |                                                                             SSO_ERROR_CREATE_DATABASE_FAILED                                                                             |
|  メッセージ テキスト   | SSO データベースの failed.%r を作成および初期化<br /><br /> SQL Server 名: %1 %r<br /><br /> SSO データベース名: % 2 %r<br /><br /> クライアント ユーザー: % 3 %r<br /><br /> エラー コード: %4 |

## <a name="explanation"></a>説明  
 このエラーは、SSO データベースを作成および初期化が失敗したことを示します。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーは次を解決するには。  

- 関連付けられているメッセージのシステムおよびアプリケーション イベント ログを確認します。  

- セットアップを再度実行します。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [SSO のインストール](../core/installing-sso.md)

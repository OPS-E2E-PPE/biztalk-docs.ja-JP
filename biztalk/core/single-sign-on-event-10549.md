---
title: 'シングル サインオン: イベント 10549 |Microsoft Docs'
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
ms.openlocfilehash: 18a3b92192c7e7e4a0906bfd35e4069dd3481d45
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993443"
---
# <a name="single-sign-on-event-10549"></a>シングル サインオン: イベント 10549
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                          |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                エンタープライズ シングル サインオン                                                                                 |
| 製品バージョン |                                                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                |
|    イベント ID     |                                                                                          10549                                                                                           |
|  イベント ソース   |                                                                                          ENTSSO                                                                                          |
|    コンポーネント    |                                                                                            CO                                                                                            |
|  シンボル名  |                                                                             SSO_ERROR_CREATE_DATABASE_FAILED                                                                             |
|  メッセージ テキスト   | SSO データベースを作成および初期化できませんでした。%r<br /><br /> SQL Server 名: %1 %r<br /><br /> SSO データベース名: % 2 %r<br /><br /> クライアント ユーザー: % 3 %r<br /><br /> エラー コード: %4 |

## <a name="explanation"></a>説明  
 このエラーは、SSO データベースを作成および初期化できなかったことを示します。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います:   

- システムおよびアプリケーションのイベント ログで関連するメッセージを確認します。  

- セットアップを再実行します。  

  詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   

- [SSO のインストール](../core/installing-sso.md)

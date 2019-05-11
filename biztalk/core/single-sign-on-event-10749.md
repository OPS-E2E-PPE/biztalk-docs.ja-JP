---
title: シングル サインオン:イベント 10749 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10986736-77c0-42a7-b2bb-cd20f9f75fa6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25392ade6b6db955a3f5d1b99086f01f920f2ff1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395476"
---
# <a name="single-sign-on-event-10749"></a>シングル サインオン:イベント 10749
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                      エンタープライズ シングル サインオン                                                                                                                      |
| 製品バージョン |                                                                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                      |
|    イベント ID     |                                                                                                                                10749                                                                                                                                |
|  イベント ソース   |                                                                                                                               ENTSSO                                                                                                                                |
|    コンポーネント    |                                                                                                                                 該当なし                                                                                                                                 |
|  シンボル名  |                                                                                                                       SSO_WARN_PS_CLIENT_PING                                                                                                                       |
|  メッセージ テキスト   | 接続先の SSO サーバーに接続できませんでした。<br /><br /> SSO サービスがそのサーバーで実行されていることと、contacted.%r ができることを確認してください。<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: % 2 %r<br /><br /> SSO サーバー名: % 3 %r<br /><br /> エラー コード: %4 |

## <a name="explanation"></a>説明  
 この警告イベントは、SSO パスワード同期が指定先 SSO サーバーを接続しないことを示します。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の 1 つ以上の操作を行います。  

- ENTSSO サーバー スナップインを使用して、サーバーを確認します。  

- 実行されていない場合は、エンタープライズ シングル サインオン サービスを開始します。  

- 接続先の SSO サーバーへのネットワーク接続を確認します。  

- 接続先 SSO サーバー上のファイアウォールを確認します。  

  詳細については、次のリソースを参照してください。  

- [サーバー スナップインを使用する方法](../core/how-to-use-the-servers-snap-in.md)

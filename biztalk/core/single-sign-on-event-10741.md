---
title: "シングル サインオン: イベント 10741 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 58b6b093-d136-498f-a3b5-c413150da956
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52ad76e20937bfa4af1dbec6d71ba59003874435
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10741"></a>シングル サインオン: イベント 10741
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10741|  
|イベント ソース|ENTSSO|  
|コンポーネント|N\A|  
|シンボル名|SSO_WARN_SAVING_REPLAY_FILE|  
|メッセージ テキスト|再生ファイルまたは進行状況ファイルを保存しています。%r<br /><br /> 保存したファイル: %1 %r<br /><br /> エラー コード: %2|  
  
## <a name="explanation"></a>説明  
 この警告イベントは、SSO が再生ファイルまたは進行状況ファイルを保存していることを示します。  
  
 ENTSSO サーバーから SSO データベースに接続できない場合、パスワード同期で再生ファイルが使用されます。 進行ファイルでは、SSO データベースとの接続が再度失われた場合に SSO で再生ファイルをどこまで読み取ることができるかを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
  
-   ユーザーの操作は必要ありません。  
  
 詳細については、次のリソースを参照してください。  
  
-   [パスワード同期](../core/password-synchronization2.md)